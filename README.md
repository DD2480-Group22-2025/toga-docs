# Report for assignment 4

## Project

Name: toga

URL: https://github.com/beeware/toga

Toga is a GUI toolkit to aid in creating applications for various platforms.

## Onboarding experience

### Did you choose a new project or continue on the previous one?

We switched to a new project, as the previous one (discord.js) wasn't as fitting for the assignment - and comes with higher stakes & complexity. Toga ([beeware/toga](https://github.com/beeware/toga)) had a comprehensive test suite which was easy to set up, and the project structure was very well documented. The project as a whole seems very inviting to contribute to, with documentation on how to get started with the process of contributing. There are also many open issues that are well suited for newcomers to contribute to, some with a "good first issue" label. We looked through these issues and found one that we thought was interesting and suitably scoped for our assignment. It was a relatively big issue, but it was conveniently split into five smaller tasks which made it easier to handle for our five-person group. Toga is a Python library that is used to create GUI applications for various platforms, and we chose to work on the issue of supporting CSS font size keywords - this meant that each person could work on one of the five backends (Android, iOS, Windows, Cocoa, GTK).

### If you changed the project, how did your experience differ from before?

Overall, it was a better experience working on this project compared to discord.js, mostly because of the comprehensive test suite, the well-documented contribution guide, and the contribution-focused nature of the project. It was also easier to comprehensively test our changes as the project is offline and not reliant on external APIs.

#### Work distribution & testing

Within the team, we have a perfect distribution of machines for the backends - 2 Macs (iOS and Cocoa), 2 Windows (Android and Winforms), and 1 Linux (GTK). This made it easy to test our changes on all platforms. Toga has a collection of different tests for various parts of the project, including the core, travertino, and tests for each backend - for every change we made, we could run the tests to ensure that we didn't break anything. Of course, every person only tested their own backend, but we made sure the tests passed for each backend before submitting our PRs into our development repo, which has been submitted as a PR to the main repo. Since Toga also has a CI pipeline, we made sure that these passed as well, which gave us confidence that our changes were correct.

#### Cache issues

One thing that took us a while to figure out, though, was that, if we made changes to some part of the codebase, we had to remove the build cache for that part of the codebase before we could test it. Otherwise, the tests would still use the old code. This was a bit annoying, and cost us some time, but once we figured it out, it was a non-issue.

## Effort spent

| topic                 | Carl | Klara | Jacob | Phoebe | Samuel |
| --------------------- | ---- | ----- | ----- | ------ | ------ |
| discussions/meetings  | 5    | 5     | 5     | 5      | 4      |
| reading documentation |      | 2     |       | 2      | 2      |
| configuration/setup   |      | 5     |       | 2      | 2      |
| analyzing code/output |      | 3     |       | 2      | 3      |
| writing documentation |      | 4     |       | 3      | 1      |
| writing code          |      | 2     |       | 4      | 5      |
| running code          |      | 4     |       | 4      | 4      |
| total                 |      | 25    |       | 22     |        |


## Overview of issue and work done.

Title: Support CSS font size keywords

URL: https://github.com/beeware/toga/issues/1814

This issue is to make sure that the font size keywords (`xx-small`, `x-small`, `small`, `medium`, `large`, `x-large`, `xx-large`, `smaller`) can be used to make it easier to create text among the 5 different backends. There are 5 architectures supported: Android, IOS, Windows, Cocoa, and GTK. These changes also need to be compatible with the testing infrastructure already in place.


## Requirements for the new feature

| Requirements                | ID  | Description                                                                                                                                                              | Linked requirement                                                                                                                                                                                                                                                                                                    |
| --------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Android Requirements        |
| 1                           | R1  | The system should allow keywords for specifying font sizes in Android. Both relative and absolute CSS keywords are represented and supported.                            | [R1 file](https://github.com/DD2480-Group22-2025/toga/blob/main/android/src/toga_android/fonts.py)                                                                                                                                                                                                                    |
| 2                           | R2  | There should be testing for Android font size keywords. Ensure that the absolute keywords and relative keywords change font-size by ~20\% with each step.                | [R2 test](https://github.com/DD2480-Group22-2025/toga/blob/main/android/tests_backend/fonts.py)                                                                                                                                                                                                                       |
| Cocoa Requirements          |
| 3                           | R3  | The system should allow keywords for specifying font sizes in Cocoa. Both relative and absolute CSS keywords are represented and supported.                              | [R3 file](https://github.com/DD2480-Group22-2025/toga/blob/main/cocoa/src/toga_cocoa/fonts.py)                                                                                                                                                                                                                        |
| 4                           | R4  | There should be testing for Cocoa font size keywords. Ensure that the absolute keywords and relative keywords change font-size by ~20\% with each step.                  | [R4 test](https://github.com/DD2480-Group22-2025/toga/blob/main/cocoa/tests_backend/fonts.py)                                                                                                                                                                                                                         |
| GTK Requirements            |
| 5                           | R5  | The system should allow keywords for specifying font sizes in GTK. Both relative and absolute CSS keywords are represented and supported.                                | [R5 file](https://github.com/DD2480-Group22-2025/toga/blob/main/gtk/src/toga_gtk/fonts.py)                                                                                                                                                                                                                            |
| 6                           | R6  | There should be testing for GTK font size keywords. Ensure that the absolute keywords and relative keywords change font-size by ~20\% with each step.                    | [R6 test](https://github.com/DD2480-Group22-2025/toga/blob/main/gtk/tests_backend/fonts.py)                                                                                                                                                                                                                           |
| iOS Requirements            |
| 7                           | R7  | The system should allow keywords for specifying font sizes in iOS. Both relative and absolute CSS keywords are represented and supported.                                | [R7 test](https://github.com/DD2480-Group22-2025/toga/blob/main/iOS/src/toga_iOS/fonts.py)                                                                                                                                                                                                                            |
| 8                           | R8  | There should be testing for iOS font size keywords. Ensure that the absolute keywords and relative keywords change font-size by ~20\% with each step.                    | [R8 test](https://github.com/DD2480-Group22-2025/toga/blob/main/iOS/tests_backend/fonts.py)                                                                                                                                                                                                                           |
| Windows Requirements        |
| 9                           | R9  | Allow keywords for specifying font sizes in Windows                                                                                                                      | [R9 file](https://github.com/DD2480-Group22-2025/toga/blob/main/winforms/src/toga_winforms/fonts.py)                                                                                                                                                                                                                  |
| 10                          | R10 | There should be testing for Windows font size keywords. Ensure that the absolute keywords and relative keywords change font-size by ~20\% with each step.                | [R10 test](https://github.com/DD2480-Group22-2025/toga/blob/main/winforms/tests_backend/fonts.py)                                                                                                                                                                                                                     |
| General System Requirements |
| 11                          | R11 | The travertino libary should support and test the use of CSS keywords `xx-small`, `x-small`, `small`, `medium`, `large`, `x-large`, `xx-large`, `smaller`, and `larger`. | [R11 constants](https://github.com/DD2480-Group22-2025/toga/blob/main/travertino/src/travertino/constants.py), [R11 file](https://github.com/DD2480-Group22-2025/toga/blob/main/travertino/src/travertino/fonts.py), [R11 test](https://github.com/DD2480-Group22-2025/toga/blob/main/travertino/tests/test_fonts.py) |
| 12                          | R12 | The CoreAPI should support and test the use of CSS keywords `xx-small`, `x-small`, `small`, `medium`, `large`, `x-large`, `xx-large`, `smaller`, and `larger`.           | [R12 file](https://github.com/DD2480-Group22-2025/toga/blob/main/core/src/toga/style/pack.py), [R12 test](https://github.com/DD2480-Group22-2025/toga/blob/main/core/tests/style/pack/test_css.py)                                                                                                                    |

## Changes made

We made changes to 20 files in total, spanning over the CoreAPI, Travertino library, Testbed suite, and the 5 different backends each of us refactored. Expand the dropdowns below to see the side-by-side changes to each of the files. 

<details> 
<summary>CoreAPI</summary>

`core/src/toga/stype/pack.py`
![image](https://github.com/user-attachments/assets/e4901d3f-a63a-4088-9416-e9efb940e939)

`core/src/toga/fonts.py`
![image](https://github.com/user-attachments/assets/130cc4ce-a766-4327-867d-ed298da84b35)

`core/tests/test_fonts.py`
![image](https://github.com/user-attachments/assets/60ef4264-8a56-42dd-be5b-ea742e837ccb)

`core/tests/style/pack/test_css.py`
![image](https://github.com/user-attachments/assets/aade6af0-a9e9-45fc-b2e8-c9d3f055f633)
</details>

<details> 
<summary>Testbed</summary>

`testbed/tests/test_fonts.py`
![image](https://github.com/user-attachments/assets/8ef8d980-1aec-47fe-935e-88258fd5e4f8)
</details>

<details> 
<summary>Travertino</summary>

`travertino/src/travertino/constants.py`
![image](https://github.com/user-attachments/assets/3e15f887-f458-4a74-9ee4-f94b51fa0df2)

`travertino/src/travertino/fonts.py`
![image](https://github.com/user-attachments/assets/fe057516-eece-4de8-b8b1-6fb026e34ee6)

`travertino/tests/test_fonts.py`
![image](https://github.com/user-attachments/assets/a4a6eb02-bc00-4702-819d-61f21e117b0a)
![image](https://github.com/user-attachments/assets/11016a16-dc1a-427b-8910-1aafc604c0c3)
![image](https://github.com/user-attachments/assets/f973b767-f5fe-46f9-99d0-a1e6264b4ed6)

</details>


<details> 
<summary>Backend Changes</summary>

`android`
![image](https://github.com/user-attachments/assets/265a90f7-b415-41e8-801f-98be57235d85)
![image](https://github.com/user-attachments/assets/df9eafce-10b1-4537-9451-5b40b4585780)

`cocoa`
![image](https://github.com/user-attachments/assets/cf991ea5-93f7-40bd-92cd-04026bda6894)
![image](https://github.com/user-attachments/assets/202bbb7a-1785-408d-bbbc-88378bd6ccc5)

`gtk`
![image](https://github.com/user-attachments/assets/105d67ca-7852-4ba8-8125-ee69095095a0)
![image](https://github.com/user-attachments/assets/bb279334-8266-4aa4-8a7d-4d0b381c09ec)
![image](https://github.com/user-attachments/assets/bfc1067f-800e-4837-a09a-4a02b53aa0a7)

`ios`
![image](https://github.com/user-attachments/assets/6e63a18a-4731-4264-bad5-4be8cc8501bd)
![image](https://github.com/user-attachments/assets/8afb49f5-8a1d-4326-bb45-74daff276752)

`windows`
![image](https://github.com/user-attachments/assets/35575557-c4ee-43e0-babe-aff9d6501cd1)
![image](https://github.com/user-attachments/assets/1c12e0e4-4094-4376-bf7f-3f61cba649f4)

</details> 

## Test results

The test results in toga are very well written with many assertions. This project contains 100% coverage report with over 2743 tests written. By running testing through `tox -m test` it runs both of the testing suites (`core` and `travertino`) and outputs the coverage results. The original results are pictured below.

<details> 
<summary>Original Results</summary>

Original test results:
![image](https://github.com/user-attachments/assets/e0269ca2-33a6-4f46-b434-fb6e9d420ac0)
![image](https://github.com/user-attachments/assets/76511778-a3e4-49cc-97bc-0824a5722a72)

Original coverage reports:
![image](https://github.com/user-attachments/assets/7ae4055f-5e73-431a-8807-e3ae8870a7d9)
![image](https://github.com/user-attachments/assets/d0cbeeaf-da71-459e-bbba-23339997eeca)

Original CI pipeline results:
![image](https://github.com/user-attachments/assets/7a782076-4acb-4362-a62b-d643da7be28e)

</details>


During our refactoring process, we created more tests to ensure that our enhancements were correct. To test our specific test updates we ran `briefcase dev --test -- test/path/test_fonts.py` from the `testbed` directory. This gave results for the specific tests relating to fonts over all of the architectures. We also were able to run `briefcase dev --test` which ran all of the tests in the testbed but it takes around 10 minutes to run. 

After refactoring, we were able to increase the number of tests and ensure that the testing coverage stayed at 100%. The results are seen below.

<details> 
<summary>Refactored Results</summary>

Refactored test results:

Refactored coverage report:

Refactored CI results:

</details>


We implemented changes in multiple locations of the testbed to ensure that both our enhancements were correct, and so that our coverage remained at 100%. Within each operating system, we added tests to check whether or not the font size was an integer or a string from the `ABSOLUTE_FONT_SIZES` or from the `RELATIVE_FONT_SIZES` and if the size matched what the expected font size should be. We updated the test suites for core and travertino to ensure that each size option (`int`, `ABSOLUTE_FONT_SIZES`, `RELATIVE_FONT_SIZE`, `SYSTEM_DEFAULT_FONT_SIZE`) was tested for each operating system. These changes allowed for us to make sure that our implementations were correct and provided full coverage. 

## UML class diagrams
Our UML class diagrams are locaed in `UML.md`.

## Way of working
We began this issue and we originally thought that the changes would not take as much time. Our plan was to finish the first issue in the first week and take a second issue for the second week. However, due to the complexity of the different requirements and testing environments for each of our systems, we continuously ran into problems regarding running the tests and making sure we had compatible systems with the operating systems we were trying to implement. 

Our team is currently in the **Working Well**. We have a good flow together and continuously keep in contact and stay on top of our commitments. In this project, we really worked together and communicated our needs so that we were able to complete the project and help each other if needed. We stuck to our guidelines that we created in the beginning. After this week, we will move to the **Retired** since this is the last project for this course. This means that our responsibilities are done and we will soon move on to new projects with different groups. We have learned a lot about working in a team and have found a system that works well for us. 

We can recognize the benefits and limitations of our work in the context of modern software engineering practices. This approach, which was guided by the SEMAT kernel, helped us maintain industry standards. We found that good documentation was really important for starting to work on already established projects. In our project for P3, the documentation helped our onboarding experience and we were able to quickly set up and move on to our analysis. In this project, while the documentation was really good and clearly stated, it was difficult to find the exact documentation that we needed to read since there were many for different versions that had key differences which were essential for running the tests and the program. Another thing we learned from this work was the importance of good testing. We found that in P3 the lack of testing really made it difficult to analyze the project. In this project, we had really great testing which also came with 100\% code coverage which made it easy to expand on their tests and to ensure that our code implementations and refactorings were correct. 


