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
|discussions/meetings |   3  |   3   |   3   |    3   |   4    |
|reading documentation|      |       |       |    1   |   2    |
|configuration/setup  |      |       |       |    1   |   2    | 
|analyzing code/output|      |       |       |    2   |   3    |
|writing documentation|      |       |       |    1   |   1    |
|writing code         |      |       |       |    3   |   5    |
|running code         |      |       |       |    3   |   4    |
|total                |      |       |       |        |        |

For setting up tools and libraries (step 4), enumerate all dependencies
you took care of and where you spent your time, if that time exceeds
30 minutes.

## Overview of issue(s) and work done.

Title: Support CSS font size keywords

URL: https://github.com/beeware/toga/issues/1814

This issue is to make sure that the font size keywords (SMALL, MEDIUM, LARGE) can be used to make it easier to create text among the 5 different backends. There are 5 architectures supported: Android, IOS, Windows, Cocoa, and GTK. 

Scope (functionality and code affected).

## Requirements for the new feature or requirements affected by functionality being refactored
| Requirement | ID | Description | Linked requirement |
|-------------|----|-------------|--------------|
|Android|
| 1 | R1 | The system should allow keywords for specifying font sizes in Android|  |
| 2 | R2 | There should be testing for Android font size keywords MEDIUM = normal size font|  |
| 3 | R3 | There should be testing for Android font size keywords SMALL = ~20\% smaller than MEDIUM|  |
| 4 | R4 | There should be testing for Android font size keywords LARGE = ~20\% larger than MEDIUM|  |
|Cocoa|
| 5 | R5 | Allow keywords for specifying font sizes in Cocoa|  |
| 6 | R6 | There should be testing for Cocoa font size keywords|  |
| 7 | R7 | There should be testing for Cocoa font size keywords MEDIUM = normal size font|  |
| 8 | R8 | There should be testing for Cocoa font size keywords SMALL = ~20\% smaller than MEDIUM|  |
| 9 | R9 | There should be testing for Cocoa font size keywords LARGE = ~20\% larger than MEDIUM|  |
|GTK|
| 10 | R10 | Allow keywords for specifying font sizes in GTK|  |
| 11 | R11 | There should be testing for GTK font size keywords|  |
| 12 | R12 | There should be testing for GTK font size keywords MEDIUM = normal size font|  |
| 13 | R13 | There should be testing for GTK font size keywords SMALL = ~20\% smaller than MEDIUM|  |
| 14 | R14 | There should be testing for GTK font size keywords LARGE = ~20\% larger than MEDIUM|  |
|iOS|
| 15 | R15 | Allow keywords for specifying font sizes in iOS| [R15 test](https://github.com/DD2480-Group22-2025/toga/blob/main/iOS/src/toga_iOS/fonts.py) |
| 16 | R16 | There should be testing for iOS font size keywords| [R16 test](https://github.com/DD2480-Group22-2025/toga/blob/main/iOS/tests_backend/fonts.py) |
| 17 | R17 | There should be testing for iOS font size keywords MEDIUM = normal size font| [R17 test](https://github.com/DD2480-Group22-2025/toga/blob/main/iOS/tests_backend/fonts.py)  |
| 18 | R18 | There should be testing for iOS font size keywords SMALL = ~20\% smaller than MEDIUM| [R18 test](https://github.com/DD2480-Group22-2025/toga/blob/main/iOS/tests_backend/fonts.py)  |
| 19 | R19 | There should be testing for iOS font size keywords LARGE = ~20\% larger than MEDIUM| [R19 test](https://github.com/DD2480-Group22-2025/toga/blob/main/iOS/tests_backend/fonts.py)  |
|Windows|
| 20 | R20 | Allow keywords for specifying font sizes in Windows| [R20 test](https://github.com/DD2480-Group22-2025/toga/blob/main/winforms/src/toga_winforms/fonts.py) |
| 21 | R21 | There should be testing for Windows font size keywords| [R21 test](https://github.com/DD2480-Group22-2025/toga/blob/main/winforms/tests_backend/fonts.py) |
| 22 | R22 | There should be testing for Windows font size keywords MEDIUM = normal size font| [R22 test](https://github.com/DD2480-Group22-2025/toga/blob/main/winforms/tests_backend/fonts.py) |
| 23 | R23 | There should be testing for Windows font size keywords SMALL = ~20\% smaller than MEDIUM| [R23 test](https://github.com/DD2480-Group22-2025/toga/blob/main/winforms/tests_backend/fonts.py) |
| 24 | R24 | There should be testing for Windows font size keywords LARGE = ~20\% larger than MEDIUM| [R24 test](https://github.com/DD2480-Group22-2025/toga/blob/main/winforms/tests_backend/fonts.py) |

## Code changes

### Patch

(copy your changes or the add git command to show them)

git diff ...

Optional (point 4): the patch is clean.

Optional (point 5): considered for acceptance (passes all automated checks).

## Test results

The test results in toga are very well written with many assertions. This project contains 100% coverage report with over 2743 tests written. By running testing through `tox -m test` it runs both the testing suite and the coverage results. The original results are pictured below. 

Original test results: ![image](https://github.com/user-attachments/assets/e0269ca2-33a6-4f46-b434-fb6e9d420ac0)

Original coverage report: ![image](https://github.com/user-attachments/assets/d0cbeeaf-da71-459e-bbba-23339997eeca)

During our refactoring process, we created more tests to ensure that our enhancements were correct. To test our specific test updates we ran `briefcase dev --test -- test/path/test_fonts.py` from the `testbed` directory. This gave results for the specific tests relating to fonts over all of the architectures. 

After refactoring, we were able to increase the number of tests and ensure that the testing coverage stayed at 100%. The results are seen below. 

Refactored test results:

Refactored coverage report: 


## UML class diagram and its description

### Key changes/classes affected

Optional (point 1): Architectural overview.

Optional (point 2): relation to design pattern(s).

## Overall experience

What are your main take-aways from this project? What did you learn?

How did you grow as a team, using the Essence standard to evaluate yourself?

Optional (point 6): How would you put your work in context with best software engineering practice?

Optional (point 7): Is there something special you want to mention here?
