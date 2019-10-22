# SDLC Navigation

0. [Home](../../README.md)
1. [Planning And Requirement Analysis](../1_PlanningAndAnalysis/README.md)
2. [Defining Requirements](../2_DefiningRequirements/README.md)
3. Design and Architecture

# 3. Design and Architecture: Design Specification

## Tech Stack

**Build and Deployment tool so it can be distributed on all OSs: [Scons](https://www.scons.org/)**

**Primary Programming language used: Python 3 or maybe JavaScript (More research on Scons is required before selection)**

## High Level Overview of Program Control Flow

1. **Parse** Flags and Args
    - Parse JSON file fed in or name of boilerplate supplied

2. Combine all input into one **Configuration**

3. **Fetch** all necessary Files/Directories/Code Snippets

4. **Build** Walk directory tree inserting:
    - Directories
    - Code Files
    - Config files

*Note on Combined Files:* execution of insertion is paused once the next specified target to be inserted is a file that is to be built from a combination of snippets, user code, or imported code. After built insertion continues.

5. Apply **Styling** if Formatter is provided

## Questions to Answer for 1st Iteration

1. **How should the user install the application?**

- *A.* .pkg Built via *Scons*
- *B.* From their package manager

2. **How to determine what package manager the user has/would like to use?**

- *A.* set it when the user uses a specific package manager to download the application
- *B.* determine the OS and check all appropriate locations if necessary
- *C.* prompt the user on first use and maybe provide an optional flag if the user would like to change it in the future

3. **How to determine if language/package for project is installed on end users system? What to do if it is not installed?**

**Potential Solutions for languages and databases**

- *A.* If not installed, prompt user to install globally
- *B.* Halt execution and tell them to go download it and supply a link

4. **What if a framework is specified that requires a build tool but there is no specified build tool in the config?**

- *A.* Have predefined defaults for each framework where the user will be prompted to select a config of
- *B.* Do *A.* but also prompt a list of available build tools (if more than one) the user can pick from
- *C.* Have a detailed error message saying a build tool must be specified that could list options

5. **How does Scons work?**

6. **What are all the acceptable keys and values of a ```config.json``` file?**

7. **How should the boilerplates be saved on the end users machine?**

**Options**

- *A.* Local database.
    - Pros: Data redundency.
    - Cons: could use to much RAM on small end user machines since SQL cells will contain files converted to bit blobs.
- *B.* Filesystem.
    - Pros: easy copy paste for creation
    - Cons: Could take up more space?

8. **How to handle building files from 1 or more code snippets and/or 1 or more complete files?**

*Problem:* It is trivial to combine multiple files into one, what the question is asking is *how is the order of insertion determined?*

*Possible Solution:* A detailed labeling/tagging system built in that can be used to determine the order of snippets in a file.

9. **What are the major components of a server-side language framework that an end user should be able to request?**

*Current list*
  - Default Setup
  - Interfacing with all currently supported front-end JavaScript frameworks
  - Different Subsets of RESTful Routing (what are they?)
  - Interfacing with all currently supported databases
  - Server-side and Client-side rendering with a framework if possible
  - Configuration with environment variables; API Keys etc.