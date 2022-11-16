# 🚩 Syllabus

## ECE495: Embedded Security Systems

## Course Goals
Cadets shall develop the skills to design, implement, test, and debug secure embedded systems.  At the end of the semester, cadets will participate the Embedded Capture the Flag (eCTF), an embedded security competition run by MITRE in partnership with Riverside Research that puts participants through the experience of trying to create a secure system. 

## Course Objectives
Cadets shall be able to:
- Write, assemble, link, and run microcontroller code in assembly and the C programming languages.
- Evaluate, analyze, debug, and modify a given program to improve its execution of a specified task.
- Designa and impelment systems that meet security and functionality requirements.
- Test security systems for functionality.
- Analyze and attack other secure embedded systems.
- Demonstrate a working knowledge of security on embedded systems.

## Course Prerequisites
ECE 382

# Course Schedule

```{note}
This schedule is subject to change as appropriate.
```
**Last Updated: 7 Nov 2022**

| Lesson  |                           Topic                           | 
|:-------:|-----------------------------------------------------------|
| 1 - 4   | Embedded Sytems Review                                    |
| 5 - 8   | Security Systems                                          |
| 9 - 12  | Wireless Communication Systems                            |
| 12 - 18 | Design a secure keyfob system for a car door lock         | 
| 19 - 21 | Prog Report / eCTF Competittion                           | 
| 22 - 26 | Lab 11 – Serial Communication   (SPI & UART)              | 
| 27 - 30 | Design a keyfob attack system                             | 
| 30 - 35 | Implement and Test a keyfob attack system                 | 
| 36 - 39 | Final report / eCTF final competition                     | 
| 40      | Final Presentation/Poster                                 | 

## Grade Distribution and Policy

The **Grade distribution** for this course is shown below.

|     Prog                  |             |     Final              |             |
|---------------------------|-------------|------------------------|-------------|
|     Labs                  |     50%     |     Labs               |     50%     |
|     Report                |     50%     |     Report             |     25%     |
|                           |             |     Final Report       |     25%     |
|     Total                 |     100%    |     Total              |     100%    |



Electrical and Computer Engineering courses are contract graded using the following 100 point scale.
<br>
|     Grade       |     Grade      |     Grade       |     Grade     |   
|:---------------:|:--------------:|:---------------:|:-------------:|
| 93 <= A <= 100  | 87 <= B+ < 90  | 77 <= C+ < 80   | 60 <= D < 70  | 
| 90 <= A- < 93   | 83 <= B < 87   | 73 <= C < 77    | 0 <= F < 60   | 
|                 | 80 <= B- < 83  | 70 <= C- < 73   |               |


## Primary Communication and Control (C2)
All communication and course material will be provided through a course and section Team. Additionally, videos will be uploaded to a YouTube channel for your convenience. Lastly, Bitbucket will be used for cadets to provide their source code for laboratories.

## Textbooks

**Optional:**
Security Engineering: A Guide to Building Dependable Distributed Systems, 3rd Edition, Ross Anderson, 2020, Wiley

Hacking: The Art of Exploitation, 2nd Edition, Jon Erickson, 2008

Network Security Essentials: Applications and Standards, 6th Edition, W. Stallings, 2017

## Collaboration Policy

Unless specifically directed otherwise, the collaboration policy for this course is:

- For all assignments in this course, unless otherwise noted on the assignment, you may collaborate with any other cadets currently enrolled in ECE 382. We expect all graded work to be in your own work. Copying another person’s work, with or without documentation, will result in NO academic credit. Furthermore, copying without attribution is dishonorable and will be dealt with as an honor code violation.
- GRs are individual efforts. No collaboration is allowed while taking these exams. All electronic devices (phones, smartwatches, computers, tablets, etc.) must be placed out of sight for the duration of the event. If any electronic device is seen during the event, the student will receive a zero for that effort. 
- Authorized resources include any material from the ECE 382 course site and online sources regarding C programming syntax only. This does not include any solutions or solution stubs for challenges similar to those asked in any assignments. 

## Documentation Requirements

- All help received on work submitted for grading must be documented in accordance with the course documentation policy. 
- Each documentation statement must be specific enough that it explicitly describes what assistance was provided, how it was used in completing the assignment, and who provided the assistance.
- If no help was received on this assignment, the documentation statement must state “None.”
- If you checked answers with anyone, you must document with whom on which problems. You must document whether you made any changes or not.  If you did make changes, you must document the problems you changed and the reasons why.
- Vague documentation statements will result in a 5% deduction on the assignment.

### Sample Documentation
Consider the following examples when writing your own detailed documentation 
statements:

Bad Example: Cadet McFly explained how the Reflectance sensors worked.

Good Example: Cadet McFly explained how the Reflectance sensors worked conceptually, using diagrams and assignment materials. **He did not look at my code nor did I look at his code** during this discussion.

Bad Example: Cadet McFly helped fix my `Reflectance_Init()` method.

Good Example: Cadet McFly helped fix my `Reflectance_Init()` method by **looking at my code** and finding that I had `P1->SEL0 &= 0x01;` instead of `P1->SEL0 &= ~0x01;` on line 85. _Note: A situation such as this may result in **less than full credit** for the `Reflectance_Init()` method, but due to the documentation statement there is no violation of the honor code._

Bad Example: Cadet McFly and I worked together on the `Reflectance_Init()` method.

Good Example: Cadet McFly and I worked together on the `Reflectance_Init()` method, each **contributing equally** to its development. Prior to this help, neither of our `Reflectance_Init()` methods were working. My `Reflectance_Init()` method is now **nearly identical** to Cadet McFly's `Reflectance_Init()` method. _Note: In a situation such as this, **at most half-credit** would be earned for the `Reflectance_Init()` method, but due to the documentation statement there is no violation of the honor code._

Bad Example: Cadet McFly showed me how the `Reflectance_Init()` method works.

Good Example: Cadet McFly showed me how the `Reflectance_Init()` method works by **letting me look at his code**. Prior to this help my own `Reflectance_Init()` method was not working.  My `Reflectance_Init()` method is now **nearly identical** to Cadet McFly's `Reflectance_Init()` method. _Note: In a situation such as this, **points would not be earned** for the `Reflectance_Init()` method, but due to the documentation statement there is no violation of the honor code._

Bad Example: Cadet McFly showed me how the `Reflectance_Init()` method works.

Good Example: Cadet McFly showed me how the `Reflectance_Init()` method works by **looking at my code and talking me through each line as I wrote it**.  Prior to this help my own `Reflectance_Init()` method was wrong.  My `Reflectance_Init()` method is now **nearly identical** to Cadet McFly's `Reflectance_Init()` method. _Note: In a situation such as this, **points would not be earned** for the `Reflectance_Init()` method, but due to the documentation statement there is no violation of the honor code._


## EI Policy

Schedule EI with an instructor if you are having difficulty with the course material.  You must have read the assignment and attempted the homework before requesting EI.  Note:  You are responsible for material if you miss class, so get notes from someone in your section.  For example, you miss the lesson where the instructor announces a quiz for the next lesson or the instructor assigns homework due next lesson.  Even though you missed the lesson, you are still responsible for the quiz, homework, or any other assignments made.  It is in your best interest to check with your classmates after an absence.  After you’ve read the assignment, attempted the homework, and checked with your classmates, you may then schedule EI if you have difficulty with the material—not to make up a class you missed.

## CAS Policy  
For CAS notification, email your instructor prior to your absence and include the lesson number, the date, and the reason (descriptive reason—don’t just send a CAS code or SCA number) as soon as possible, preferably before the absence occurs.  It is your responsibility to check your SCA to see if instructor permission is required.  If it is, you must make the request prior to your absence.  If you miss class, you are responsible for all material (e.g. assignments, notes, announcements, handouts, etc.) covered in class.  Please check with another cadet in your section to find out what you missed.  

When a cadet is absent on the day that an assignment is due, or on the date of a quiz or GR, the cadet is responsible for meeting the following standards: 
- Scheduled Absence: If a cadet will miss any graded event due to a scheduled absence such as an SCA, sport team trip, or scheduled lasik surgery, the cadet is expected to complete all work BEFORE the absence.  
- Unscheduled Absence: If a cadet misses a graded event for an unscheduled reason such as AOC approved bedrest or a family emergency, the cadet must complete all work on the first full class day that they return to duty in order to avoid a late penalty.  For example, if a cadet is on AOC bedrest for a GR on M17 and can return to duty on T17 or M18, the cadet is expected to make up the work by M18.
- Unique Circumstances: For circumstances that do not fall under either of these broad categories (e.g. concussion protocol), the cadet is expected to communicate early and often with the instructor.  The instructor and course director will work with the cadet on a course of action.

## Late Work Policy
All work is due as shown on Gradescope. If problems arise with graded assignments, see your instructor in advance. 
- The cutoff for on-time submission is 0700 on the due date. 
- Late days are counted in 24-hour periods. Submitting between 07:00:01 on the due date and 07:00:00 the next day is one day late, and so on.
- You are given 5 grace days (self-granted extensions) which you can use to give yourself extra time without penalty. No more than 2 grace days can used for each assignment.
- Instructor-granted extensions are only considered after all grace days are used and only given in exceptional situations. Computer problems such as hard-drive reimaging are not considered as exceptional situations and you must use grace days.
- Late work handed in when you have run out of grace is discounted 30% for the first day late and 10% per day late thereafter.
- Every assignment has a hard deadline; 4 calendar days past the original due date. 
- Late submissions (penalty or not) are not accepted after the hard deadline or after the solution to the assignment is published. No late submissions (penalty or not) will be accepted for the assignments right before GRs.

## Assignments
Assignments and due dates are included in Gradescope.

## Laboratories
Labs are held in 2E48, but may include a prelab assignment that must be done before coming to class.  The labs tend to be very hardware/software intensive and will probably require debugging to isolate and fix problems.  In-class time is your primary chance to get active help for these problems so the more you prepare outside of class, the more successful you’ll be.  The 53 minutes go by extremely fast - don’t waste them!

## Final Project
The final project will be a culmination of the learned material and will include a robot maze and competition. The final project will include a formal laboratory write-up and seven-minute presentation describing your design, solution, and results. The final project is worth 25% of your final grade.

## Miscellaneous
This course is designed to help in your development as an engineer or cyber scientist.  Feel free to provide feedback on the lessons and labs at any time.  If you have ideas to improve or enhance the course, please let me know.  The class builds on concepts from the prerequisites, so it is important for you to seek help as soon as you need it.   Procrastination is truly the enemy in a hardware design course.  A little foresight and planning and a lot of effort will result in an extremely rewarding experience serving as the basis for future microprocessor design work.
