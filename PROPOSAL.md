# Project Proposal

![image](https://user-images.githubusercontent.com/25606213/207461137-0a39a046-205b-4c48-9439-5f06e01f1ce9.png)

## Idea

For this project we want build a CI/CD system for a simple application with the use of Tekton.


### Description

We want to get familiar with Tekton and the Art of implementing a CI/CD system. 

Defining the exact implementation steps is difficult without the full knowledge of the potental of Tekton. This we will gain during Milestone 1 and add in the README. 

Our goal is to explore and understand the potential of Tekton and also tap into some corner cases. We will implement our findings and conclude them in a demonstration for the final presentation.


## Milestones

### Milestone 1 (Understanding Tekton & Setup - 25.12.2022)
- Get familiar with Tekton, what it is, what it does and how it basically works. Finish the tutorial & look through their documentation.

- First draft and setup. Install Tekton on our clusters. Develop a simple application that will be used for the pipeline.


### Milestone 2 (Implementing our Project - 15.01.2023)
- Define some *Steps* (e.g., executing some unit tests, linting, etc.), group them in *Tasks* (YAML) and apply those tasks to our cluster.
- Also, choose some tasks from the *Tekton Catalog* and install those as well.
- Define a *Pipeline* (YAML) as a collection of tasks. 
- Execute the pipeline and tasks by creating *PipelineRun*s (there are also *TaskRun*s) and observe logs.
- After the manual execution from above, try to automate this process by defining a Tekton *Trigger*, which creates a run automatically on demand (e.g., after a developers does a git push). 

### Milestone 3 (Submission - 18.01.2023)
- Test our implementation.
- Create a demonstration.
- Write a documentation.
- Prepare a presentation for the final lecture.


## Responsibilities

This technology is new for us and we aim to learn all parts of it, we try to work together and include everyone in the process of implementing Milestone 2. Because our scope will also be completely clear after Milestone 1, we can decide to further split responsibilities there. Once the main project is implemented (Milestone 2 is finished) we will devide the work for the final submission as follows:

**Eva**
- Demo

**Tim**
- Documentation

**Daniel**
- Presentation
