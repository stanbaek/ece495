# 🙋 FAQ

(faq-general)=
## General

### _How are the bonus points used for my final grade?_

The bonus points (anything above 50) earned in your labs and homework assignments will be used for your other labs and homework assignments, respectively.   

Here is how to calculate the final lab grade. Let $L_k$ be your Lab $k$ grade. The final lab grade, $L_f$ will be

$$ L_f = \min(50, L_{ave}) = \min(50, \frac{1}{N}\sum L_k) $$

Since there are 15 labs (Lab2, Lab3, ..., Lab17), $N$ will be 15.  Note that there is no Lab9, and Lab _a_ and Lab _b_ are considered one lab, e.g., Lab13a and Lab13b.

Suppose we have three labs and your lab scores are 47, 48, and 49. Then, the average of the 3 lab scores is 48, and min(50, 48) = 48. So, your final lab grade will be 48. If your scores are 49, 50, and 54, the average is 51 and min(50, 51) = 50.  Therefore, your final lab grade will be 50.  The bonus points earned in labs will only be used for your final lab grade.  They can't be transferred to homework, GRs, or the final project.

Your final homework grade will be calculated in the same way. The bonus points earned in homework will only be used for your final homework grade.

There are also bonus points in the final project, which can be used towards the final grade.
If you earn 300/300 for the final project, the contribution of your final project to the final grade will be 25% because the final project is worth 25% of the final grade.  If you earn 330/300 for the final project, the contribution of your final project towards the final grade will be 27.5% - you can easily change your final letter grade.  Note that you are eligible for 
the final project bonus points only if you complete all the lab demos.


(faq-assembly)=
## Assembly

### _Why do I need to preserve R2 before calling my function if it only uses R0 and R1?_
 
According to AAPCS, a subroutine can freely modify R0-R3 & R12.  You claim that "my" function only uses R0 and R1.  First, when you develop software/hardware, there is no such thing as "my" product.  It does not belong to you.  All the code you develop belongs to your team, not you.  I have never seen an engineer/programmer works on their own like Tony Stark. Engineers/programmers work in a team of ~10 - 1000 and anyone in the team can modify your code.  So, you MUST comply with standards.  Second, you may want to claim that my approach is more efficient.  It is not a matter of efficiency.  You must stop at a stop sign whether a car is coming or not.  The same applies to many other standards such as safety standards.  So, always remember that R0-R3 & R12 can hold different values after calling subroutines.

### _Why does ADD not update Program Status Register (PSR)?_

The textbook (pp. 64) says, "The N, Z, V, C, and Q bits give information about the result of a previous ALU operation." 
 
Although ADD and SUB are ALU operations, they do not update the PSR register. If you want to update them, you must use ADDS and SUBS instead.  CMP always updates the PSR flags.  
 
With SUBS you can replace
```asm
    SUB R0, #1   ; R0 = R0 - 1
    CMP R0, #0   ; R0 == 0 ?
    BEQ  Label1  ; go to Label1 if R0 == 0
``` 
with
```asm 
    SUBS R0, #1   ; R0 = R0 - 1
    BEQ  Label1   ; go to Label1 if R0 == 0, EQ tests Z == 1
```


### _How to push and pop registers?_

First, you need curly brackets on the registers for push and pop i.e. `PUSH {LR}`. Here is how to push and pop multiple registers.
```
    PUSH {R4-R6}
    PUSH {R9}
    PUSH {LR}

    POP {LR}
    POP {R9}
    POP {R4-R6}
```
The push and pop operations use a memory stack, accessed in an orderly manner called last-in-first-out (LIFO). So, the last thing you push must be popped first. Here are elegant ways to push and pop multiple registers.
```
    PUSH {R4, R5, R6, R9, LR} 
    POP {R4, R5, R6, R9, LR}  ;  same order

    ; even better way
    PUSH {R4-R6, R9, LR}
    POP {R4-R6, R9, LR}       ;  same order
```

When you push and pop multiple registers, the order does not have to be the same for ARM 32-bit processors because they always go into the same relative positions, regardless of the order of appearance inside the curly brackets ({ }). The lowest-numbered register is stored and loaded first when you push and pop multiple registers in a single pop/push instruction, e.g., the last two examples above. 


### _Can R0 and R1 be saved in the Stack (Push/Pop)? I thought it was only R4-R11 that would be able to be stored in a stack_

Yes, they _can_ be stored in the stack, whereas R4-R11 _must_ be because you have to restore them if you change them in your function. You can store R0-R3, R12 in the stack to preserve them before calling a function in case the function contaminates them.  However, you don't want to do that because it takes time.  Memory access is generally  ~100-1000 times slower than register access. So, you had better store R0-R3 to R4-R11 instead.  

You may insist you would not want to push R4-R11 if you are using them for R0-R3, which still causes memory to be used. You are right, but if you have used R4-R11 for something else, you have already pushed them. Otherwise, there is no reason to push R0-R3 because a function can freely modify R0-R3. 


(faq-c_programming)=
## C Programming Language

### _What is the switch statement, and how does it work?_

The switch statement is a multi-way decision that tests whether an expression matches one of several constant integer values and branches accordingly.

```C
switch (expression) {
    case const-expr:  
        statements
        break;
    case const-expr:  
        statements
        break;
    default:
        statements
        break;
}
``` 

If you don't add `break`, the program will flow through the following case statements.  Here is an example

```C
int nwhite, nother, ndigit[10]; 

while ((ch == getchar()) != EOF) {
    switch (ch) {
        case '0':   case '1':  case '2' :  case '3': case '4' :       
        case '5':   case '6':  case '7' :  case '8': case '9' :   
        // if ch is between '0' and '9'
            ndigit[ch-'0']++;
            break;
        case ' ': 
        case '\n':
        case '\t':   
        // if ch is a space, \n, or \t
            nwhite++;
            break;
        default:
            nother++;
            break;
    }
}
``` 
Reference: B. Kernighan & D. Ritchie, "The C Programming Language," 2nd ed, pp. 58, 1988, Pearson Education.**

### _What is the _static_ qualifier?_

The functions inside C files are by default *global* functions.  Although they are not declared in the associated .h files, the functions can be seen (and even called - I don't want to show you how because it is not good practice) by other files. So, you will have a compile error if you have two functions with the same name in two C files.  
 
Then, how can you make the function invisible to other files?  Use the *static* qualifier.  It makes your functions private in the C file they are defined. 
 
Variables declared outside functions are also global variables, and other files can see them.  They can also be static to make them private (again invisible by other files) - this is different from the static variables inside a function. 

(FAQ:CCS)=
## CCS

### _How to comment out a block of code in CCS?_

To comment out and uncomment multiple code lines, `Ctrl+/`

### _How can I use git inside CCS?_

CCS comes with built-in GIT, and it can be opened from CCS menu > View > Other > Git > Git Staging. You can commit and push at the same time.


(FAQ:HardwareSoftwareInterface)=
## Hardware/Software Interface

### _Why does my bump sensor not reset to 0 after the sensor is decompressed?_

Your pull-up/down resistors may not be configured appropriately.

### _Why would my robot run for maybe half a second and then stop? It worked when I did my demos a couple of days ago, and I don’t think I have changed any code._

Batteries might be dying.


### _I have two switches on my robot. Which one should I use?_

There are two switches on your robot as shown below. Keep the slide switch in the yellow rectangle in the off position and use the button switch in the yellow circle to turn the robot on and off.   

```{image} ./figures/RSLK_Switches.PNG
:width: 640
:align: center
```
<br>



### _How to run the hardware diagnostics tool for hardware issues on my robot?_

There may be a situation where you wonder whether it's your code or the hardware that's not working. Here is how to test your hardware.

:::{note}
You need 6 AA batteries to run this tool.
:::

- Download {Download}`HardwareDiagnostics.out<./files/HardwareDiagnostics.out>`.
- Connect the LaunchPad to your computer.
- Open Code Composer Studio (CCS) and select your workspace.
- Ensure your Project Explorer is open on the left of the CCS screen. If not, select `Project Explorer` under `View`.
- Select any project by clicking it. You don't have to open it.
- Select `Load` under the `Run` menu or click the `Flash` button on the toolbar.
- Click `Select Program to Load`.
- Clock `Browse` to open `HardwareDiagnostics.out` you downloaded. **Do not use the `HardwareDiagnostics.out` under the HardwareDiagnostics project** shown in the gif below.
- It will flash the hardware diagnostics program in your microprocessor. 

```{image} ./figures/HardwareDiagnostics.gif
:width: 760
:align: center
```
<br>
