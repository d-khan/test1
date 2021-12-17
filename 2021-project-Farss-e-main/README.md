# ST101 Programming for Data Science

## Project

### 2021/22 Michaelmas term

---

The maximum mark for the project is 100

* Due date: 20/1/2022 12noon
* Hard deadline: 27/1/2022 12noon

**It is a summative assessment and it accounts for 70% of your final grade.** Requests for extensions are only granted in exceptional circumstances. In particular, no extension will be granted for job related applications, late course add drop, clash with other course work, etc. 10 marks (out of 100 marks) will be deducted for a late submission in every 24 hours. Any submission after the hard deadline will automatically receive 0 marks.

**Your work will only be treated as submitted if you have done all of the following:**
1. Sign the plagiarism statement below with your _candidate number_
2. Submit your work (including this README.md file with the Plagiarism statement signed) via GitHub as usual

---

## Plagiarism statement

Plagiarism is an examination offence and carries heavy penalties.

I declare that, this submission is my own work and contains no plagiarism. I have read and understood the plagiarism policy for this project stated below and the Schoolʹs [policy on plagiarism](https://www.lse.ac.uk/social-policy/Current-Students/Plagiarism).

Your 5-digit candidate number: _______

---

## Objectives

The project serves as the most important coursework for us to assess your progress in the course in terms of:
* Understanding of the course materials
* Ability to apply the course materials on real life problems using programming
* Other skills like self learning skills

To allow us to be able to assess the qualities above, you are asked to complete 3 programming tasks and write a report to show your results (See the section `Tasks` for more details). You are also required to use the programming concepts/tools listed under the section `Concepts/tools you must use` to show that you are capable of applying _all_ the programming concepts/tools we have learned in this course.

---

## Tasks

In the project, we will perform some programming tasks to extend what we have done for the PS5, PS8 and PS11. In the previous problem sets, we have done the following:

* Doing some tasks on a subset of arXiv data to, for example, find out the productive authors
* Implement a simple Nim game with "naive" and "smart" players
* Analyse the UK coronavirus data

In the project, we will work on similar problem/data but this time the task 1 and 2 are inspired by some actual data science applications/findings:

1. (40 marks) Investigate if the "friendship paradox" that is often observed in social network data is present in the arXiv data. See [friendship_paradox.md](friendship_paradox.md) for further instructions
2. (40 marks) Create the class `LearningPlayer` to play the Nim game using a strategy inspired by reinforcement learning. See [nim_reinforcement.md](nim_reinforcement.md) for further instructions
3. (20 marks) Analyse the coronavirus data to compare and explain the difference observed between two different countries. See [coronavirus.md](coronavirus.md) for further instructions

**All the code must be submitted.**

You are also required to write a report in a Jupyter Notebook in [`src/report.ipynb`](src/report.ipynb) to summarise your program and findings in the following structure:

1. Short introduction
    * What you are going to do in this project
2. Task 1
3. Task 2
4. Task 3
5. Conclusion and reflection
    * What you have achieved and found
    * What are the limitations
    * What can be improved (in terms of both implementation and analysis) or what other functionality/analysis you may want to add if you have more time and resources

For each task, you must state clearly in the report where the corresponding code is (if they are not in the report). For what you need to include in the report for task 1-3, please refer to the corresponding instructions.

---
## Concepts/tools you _must_ use

In order to get a high mark for the project, you _must_ use _all_ of the following in your project <ins>appropriately</ins>:

* Basics: control flow and containers
* Functions: abstraction and decomposition
  * Your submission must include at least one function / module
* Modules: modularisation
  * Your submission must have at least one .py file serves as a module and import at least one module / library
* At least one library not demonstrated (but it can be _mentioned_) in the course
  * E.g. `matplotlib`
* Good practice: testing, assertion, use of comments, etc
  * Your submission must include at least one test
* OOP: encapsulation, abstraction, composition, inheritance
* Important data science tools including `Numpy` or `Pandas` (with vectorised operations) and Jupyter Notebook

See the marking criteria below for more details.

If you think that some concepts/tools above are not appropriate for what you want to do, please contact the lecturer and we will see if such omission can be accepted, or alternative arrangement can be made.

---
## Knowledge that you _may_ consider to demonstrate

* Programming paradigms
* Debugging
* Error raising and handling

---

## List of modules / libraries / data structure that you can use

You can use the tools below without the need of getting permission from the lecturer:

* `random` and `datetime`, and any of the functionality provided by it
* `set` and any of the functionality provided by it
* `Pandas` and `Numpy`, but you can only use them for the tasks that specified that you can use them, or you use them for some "additional" / "optional" features, or you have got the approval from the lecturer
* `matplotlib` library

For any "optional" or "additional" functionality / analysis that you want to add, there is no restriction on what you can use.

For any other modules / libraries / data structure / unseen built-in methods that you want to use, please get the permission from the lecturer. Moodle will also keep a list of approved modules / libraries / data structure / unseen built-in methods so please have a look as well. You will be penalised if you are using unauthorised modules / libraries / data structure / unseen built-in functions, etc. in your project.

---

# Plagiarism policy

* Misconduct can lead to a zero for the entire coursework element or more serious consequence
* Your submission must be 100% your own work. It means that (_unless_ you are told otherwise / you have got the permission from the lecturer):
    * All the code must be written by yourself
    * You _cannot_ use **(unless it is stated otherwise in the question)**
      * Any modules and libraries that are not listed above
        * Even for modules that we have seen like `math`, you are _not_ allowed to use them unless it is stated otherwise in the question
      * Any Built-in functions (including methods), types, operators and other functionalities that are _not_ covered or demonstrated in the course or not listed above
        * Even for the things that we have _mentioned_ like `bin()` (it is mentioned because we asked you not to use it for PS2), you are _not_ allowed to use them
        * You are allowed to use the ones that have been _covered_ or _demonstrated_ in the lectures, workshops and problem sets (including the solutions). Appendix and exercises for self-study are also included
    * You _cannot_ **(unless it is stated otherwise in the question)**
      * Search anything related to the coursework. In particular, you must NOT search for answers online
      * Reference to or borrow _any_ materials other than the course materials (except the ones stated in the questions)
      * Have any form of communication with your fellow classmates or any other people except the lecturer (e.g. fellow classmates, previous students, your parents, someone you pay to help you to do the coursework) about the summative work between the release date and the hard deadline. This includes (but does not restrict to):
        * Showing, discussing, viewing, copying the solution to/from other people
        * Having someone else to do your work
        * Talking about the assignments (including discussing the difficulty levels of the assignments) and your approach to solving them with others
* We take plagiarism seriously. You will need to submit your code to Moodle to determine the similarity with other works via Turnitin. Any suspicious plagiarism will be reported for further investigation

If in doubt, always ask the instructor for clarification.

---

## Marking criteria

Your grade will be given based on:

| Criteria           | Details                                            |
|:-------------------|:---------------------------------------------------|
| Sanity             | Fulfil the required functionality                  |
| Programming skills | Appropriate use the required programming concepts and tools covered in the course |
| Robustness         | Encapsulation and data integrity |
| Efficiency         | Speed of the program |
| Readability        | Good variable, function, class and module names; Appropriate comments, no confusing whitespace, etc. |
|                    | Every function, class and module _must_ have an _informative_ and _abstract_ docstring (exception: small helper functions) |
| Style              | Following the naming convention for variables, functions, modules and classes, and prevent dangerous code like using built-in function names or types as variable names, etc. |
| Program design     | Decomposition and abstraction: use of functions, modules and classes to decompose the problems, structure your code and make your code manageable for a relatively complex problem |
|                    | Easy to maintain - prevent redundant, unnecessary or copy-and-paste code |
| Testing            | Appropriate use of testing (glass box and / or black box approach) to make sure your program works as intended |
| Self learning      | Learn how to use an unseen library to solve the problem in hand |
| Analysis and reflection | Sensible analysis on the data. Reflection on limitations and possible improvements on the program and data analysis |
| Communication      | Clear and sensible structure with introduction and conclusion, effective communication (including effective use of Jupyter Notebook)|

You need to have the characteristics below to get the corresponding mark:

| Mark | Characteristics                                           |
|:-----|:----------------------------------------------------------|
|85-100| Excellent understanding of course materials: appropriate and effective use of all the tools required |
|      | Excellent coding skills: code executes (nearly) perfectly and  well-designed with good readability and style, with appropriate (and ideally thorough) testing and robust code development |
|      | Go further and beyond: demonstrate the self learning skill with effective use of unseen libraries. Implementing sensible improvements and additional functionality to the program and/or provide follow up analysis |
|      | Sensible analysis: relevant, appropriate and well-motivated analysis with reflection on the results and limitations. While due to the time limit the analysis may not be very thorough, some meaningful results are expected (showing something that is not working also counts) |
|      | Well written report: Self-contained report with appropriate examples showing _how_ the program works, effective presentation of the results and a good conclusion with discussion about possible improvements |
|70-84| Excellent understanding of course materials: appropriate and effective use of all the tools required |
|      | Excellent coding skills: code executes (nearly) perfectly and  well-designed with good readability and style, with appropriate (and ideally thorough) testing and robust code development |
|      | Self learning skill: good use of one or more unseen libraries |
|      | Sensible analysis: relevant, appropriate and well-motivated analysis with reflection on the results and limitations |
|      | Well written report: Self-contained report with appropriate examples showing _how_ the program works, effective presentation of the results and a good conclusion with discussion about possible improvements |
|60-69 | Good understanding of course materials: appropriate use of most of the tools required |
|      | Good coding skills: code executes mostly fine, generally well-designed with relatively good readability and style, with appropriate testing |
|      | Self learning skill: good use of one or more unseen libraries |
|      | Sensible analysis: appropriate and sensible analysis |
|      | Good report: complete report with clear presentation of the results |
|50-59 | Generally good understanding of course materials: appropriate use of majority of the tools required |
|      | Good coding skills: code executes and fulfil majority of the requirements, showing the ability to solve problems with programming. Acceptable readability and style with some testing |
|      | Self learning skill: using one or more appropriate unseen libraries in the right direction |
|      | Analysis: correct analysis in the right direction |
|      | Good report: report has all required parts, including clear presentation of the results |
|40-49 | Understanding of course materials: able to use the majority of the tools required |
|      | Coding skills: code may not run correctly but demonstrates some good understanding of the syntax and concepts, with an attempt to have the right readability, style, testing etc. |
|      | Self learning skill: good attempt to use one or more appropriate unseen libraries |
|      | Analysis: good attempt to do a sensible analysis |
|      | Report: report has all required parts, results are displayed |
|0-39  | Poor understanding of course materials: not able to correctly use the majority of the tools required |
|      | Poor code skills: code does not work, or demonstrates a lack of knowledge of basic syntax and concepts, poor readability and style. No testing or wrong testing |
|      | Poor self learning skill: wrong use or does not show the effort of using any unseen library appropriately |
|      | Poor analysis: no attempt to do the analysis or the analysis is not sensible |
|      | Poor report: poor structure and ineffective communication. Some parts like introduction and analysis results is missing |

**To get 60 or above, _serious attempt_ to fulfil ALL the requirements is required.**

---
## Note

* Remember that you are required to use _all_ tools listed above
