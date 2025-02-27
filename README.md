# Report for assignment 4

## Project

Name: toga

URL: https://github.com/beeware/toga

Toga is a GUI toolkit to aid in creating applications for various platforms. 

## Onboarding experience

Did you choose a new project or continue on the previous one?

If you changed the project, how did your experience differ from before?

## Effort spent
|topic                | Carl | Klara | Jacob | Phoebe | Samuel |
|---------------------|------|-------|-------|--------|--------|
|discussions/meetings |   3  |   3   |   3   |    3   |   3    |
|reading documentation|      |       |       |        |        |
|configuration/setup  |      |       |       |    1   |        | 
|analyzing code/output|      |       |       |        |        |
|writing documentation|      |       |       |    1   |        |
|writing code         |      |       |       |        |        |
|running code         |      |       |       |        |        |

For setting up tools and libraries (step 4), enumerate all dependencies
you took care of and where you spent your time, if that time exceeds
30 minutes.

## Overview of issue(s) and work done.

Title: Support CSS font size keywords

URL: https://github.com/beeware/toga/issues/1814

This issue is to make sure that the font size keywords (SMALL, MEDIUM, LARGE) can be used to make it easier to create text among the 5 different backends. There are 5 architectures supported: Android, IOS, Windows, Cocoa, and GTK. 

Scope (functionality and code affected).

## Requirements for the new feature or requirements affected by functionality being refactored
| Requirement | ID | Description |
|-------------|----|-------------|
|Android|
| 1 | R1 | The system should allow keywords for specifying font sizes in Android|
| 2 | R2 | There should be testing for Android font size keywords MEDIUM = normal size font|
| 3 | R3 | There should be testing for Android font size keywords SMALL = ~20\% smaller than MEDIUM|
| 4 | R4 | There should be testing for Android font size keywords LARGE = ~20\% larger than MEDIUM|
|Cocoa|
| 5 | R5 | Allow keywords for specifying font sizes in Cocoa|
| 6 | R6 | There should be testing for Cocoa font size keywords|
| 7 | R7 | There should be testing for Cocoa font size keywords MEDIUM = normal size font|
| 8 | R8 | There should be testing for Cocoa font size keywords SMALL = ~20\% smaller than MEDIUM|
| 9 | R9 | There should be testing for Cocoa font size keywords LARGE = ~20\% larger than MEDIUM|
|GTK|
| 10 | R10 | Allow keywords for specifying font sizes in GTK|
| 11 | R11 | There should be testing for GTK font size keywords|
| 12 | R12 | There should be testing for GTK font size keywords MEDIUM = normal size font|
| 13 | R13 | There should be testing for GTK font size keywords SMALL = ~20\% smaller than MEDIUM|
| 14 | R14 | There should be testing for GTK font size keywords LARGE = ~20\% larger than MEDIUM|
|iOS|
| 15 | R15 | Allow keywords for specifying font sizes in iOS|
| 16 | R16 | There should be testing for iOS font size keywords|
| 17 | R17 | There should be testing for iOS font size keywords MEDIUM = normal size font|
| 18 | R18 | There should be testing for iOS font size keywords SMALL = ~20\% smaller than MEDIUM|
| 19 | R19 | There should be testing for iOS font size keywords LARGE = ~20\% larger than MEDIUM|
|Windows|
| 20 | R20 | Allow keywords for specifying font sizes in Windows|
| 21 | R21 | There should be testing for Windows font size keywords|
| 22 | R22 | There should be testing for Windows font size keywords MEDIUM = normal size font|
| 23 | R23 | There should be testing for Windows font size keywords SMALL = ~20\% smaller than MEDIUM|
| 24 | R24 | There should be testing for Windows font size keywords LARGE = ~20\% larger than MEDIUM|

## Code changes

### Patch

(copy your changes or the add git command to show them)

git diff ...

Optional (point 4): the patch is clean.

Optional (point 5): considered for acceptance (passes all automated checks).

## Test results
Original test results: ![image](https://github.com/user-attachments/assets/e0269ca2-33a6-4f46-b434-fb6e9d420ac0)

Overall results with link to a copy or excerpt of the logs (before/after
refactoring).

## UML class diagram and its description

### Key changes/classes affected

Optional (point 1): Architectural overview.

Optional (point 2): relation to design pattern(s).

## Overall experience

What are your main take-aways from this project? What did you learn?

How did you grow as a team, using the Essence standard to evaluate yourself?

Optional (point 6): How would you put your work in context with best software engineering practice?

Optional (point 7): Is there something special you want to mention here?
