<!-- The previous outline, which includes some ideas I haven't covered in my lecture

# General Concepts

- Programming languages types and paradigms
    - Machine language instructions
    - Assembly instructions
    - High-Level Programming Languages
    - Object-oriented paradigm and  data hiding
- The difference between roles (user, tester, programmer)
- How complex piece of software _reuse_ previous pieces.
- The importance of security :lock:
    - Types of attack (malware, phishing, social engineering, zero-day) 
    - Types of loss (loss of integrity / availability / confidentiality)

## Writing and Compiling Programs

- Understand what the "flow of development" is:
    - Having a goal
    - Writing down specifications
    - Creating the source code
    - Running the compiler
    - Reading the compiler's output, warning and error messages
    - Looking for documentation and help on-line and off-line
    - Testing
    - Making sure the program is secure :lock:
    - Editing
    - Reusing
- Using an IDE to
    - Create a project, 
    - Perform some of the steps of the "flow of development",
    - Correctly save and re-open projects,
    - Understand basic features of break points and debugging. :question:

## Computer Usage

- How to download and install an IDE in a secure way :lock:
- How to share and zip a project
- How to use shortcuts :question:
- How to look for on-line documentation

-->

# Introduction to Computers and Programming

## Principles of Computer Programming

- Computer hardware changes frequently - from room-filling machines with punch cards and tapes to modern laptops and tablets
- With these changes - the capabilities of computers increase rapidly (storage, speed, graphics, etc.)
- Computer programming languages also change
    - Better programming language theory leads to new programming techniques
    - Improved programming language implementations
    - New languages are created - old ones updated
- There are hundreds of programming languages, why?
    - Different tools for different jobs
        - Some languages are better suited for certain jobs
        - Python for scripting, Javascript for web pages          
    - Personnel preference and popularity
- This class is about "principles" of computer programming
    - Common principles behind all languages won't change, even though hardware and languages do
    - How to organize and structure data
    - How to express logical conditions and relations
    - How to solve problems with programs

## Programming Language Concepts

We begin by discussing three categories of languages manipulated by computers.
We will be studying and writing programs in _high-level languages_, but understanding their differences and relationships to other languages^[That will be studied in the course of your study if you continue as a CS major.] is of importance to become familiar with them.

- Machine language
    - Computers are made of electronic circuits
        - Circuits are components connected by wires
        - Some wires carry data - e.g. numbers
        - Some carry control signals - e.g. do an add or a subtract operation
    - Instructions are settings on these control signals
        - A setting is represented as a 0 or 1
        - A machine language instruction is a group of settings - For example: 1000100111011000
    - Most CPUs use one of two languages: x86 or ARM
- Assembly language
    - Easier way for humans to write machine-language instructions
    - Instead of 1s and 0s, it uses letters and "words" to represent an instruction. 
        - Example x86 instruction: `MOV BX, AX` which makes a copy of data stored in a component called AX and places it in one called BX
    - **Assembler**: Translates assembly language instructions to machine language instructions
        - For example: `MOV BX, AX` translates into `1000100111011000`
        - One assembly instruction = one machine-language instruction
        - x86 assembly produces x86 machine code
    - Computers can only execute the machine code
- High-level language
    - Hundreds including C#, C++, Java, Python, etc.
    - Most programs are written in a high-level language since:
        - More human-readable than assembly language
        - High-level concepts such as processing a collection of items are easier to write and understand 
        - Takes less code since each statement might be translated into several assembly instructions
    - **Compiler**: Translates high-level language to machine code
        - Finds “spelling” errors but not problem-solving errors
        - Incorporates code libraries – commonly used pieces of code previously written such as Math.Sqrt(9)
        - Optimizes high-level instructions – your code may look very different after it has been optimized
        - Compiler is specific to both the source language and the target computer
    - Compile high-level instructions into machine code then run since computers can only execute machine code

!["A Visual Representation of the Relationships Between Languages"](img/overview_languages_1)

A more subtle difference exist between high-level languages.
Some (like C) are _compiled_ (as we discussed above), some (like python) are _interpreted_, and some (like C#) are in an in-between called _managed_.


- Compiled vs. Interpreted languages
    - Not all high-level languages use a compiler - some use an interpreter
    - **Interpreter**: Lets a computer "execute" high-level code by translating one statement at a time to machine code
    - Advantage: Less waiting time before you can run the program (no separate "compile" step)
    - Disadvantage: Program runs slower since you wait for the high-level statements to be translated then the program is run
- Managed high-level languages (like C#)
    - Combine features of compiled and interpreted languages
    - Compiler translates high-level statements to **intermediate language** instructions, not machine code
        - Intermediate language: Looks like assembly language, but not specific to any CPU
    - **Runtime** executes by *interpreting* the intermediate language instructions - translates one at a time to machine code
        - faster since translation step is partially done and only its last step is done when running the program  
    - Advantages of managed languages:
        - In a "non-managed" language, a compiled program only works on one OS + CPU combination (**platform**) because it is machine code
        - Managed-language programs can be reused on a different platform without recompiling - intermediate language is not machine code and not CPU-specific
        - Still need to write an intermediate language interpreter for each platform (so it produces the right machine code), but, for a non-managed language, you must write a compiler for each platform
        - Writing a compiler is more complicated and more work than writing an interpreter thus an interpreter is a quicker (and cheaper) way to put your language on different platforms
        - Intermediate-language interpreter is much faster than a high-level language interpreter, so programs run faster than an "interpreted language" like Python
    - This still runs slower than a non-managed language (due to the interpreter), so performance-minded programmers use non-managed compiled languages (e.g. for video games)

!["A Visual Representation of the Differences Between High-Level Languages"](img/overview_languages_2)


## Software Concepts

- Flow of execution in a program
    - Program receives input from some source, e.g. keyboard, mouse, data in files
    - Program uses input to make decisions
    - Program produces output for the outside world to see, e.g. by displaying images on screen, writing text to console, or saving data in files
- Program interfaces
    - **GUI** or Graphical User Interface: Input is from clicking mouse in visual elements on screen (buttons, menus, etc.), output is by drawing onto the screen
    - **CLI** or Command Line Interface: Input is from text typed into "command prompt" or "terminal window," output is text printed at same terminal window
    - This class will use CLI because it's simple, portable, easy to work with -- no need to learn how to draw images, just read and write text


## Programming Concepts

- Programming workflow (see flowchart)
    - Writing down specifications
    - Creating the source code
    - Running the compiler
    - Reading the compiler's output, warning and error messages
    - Fixing compile errors, if necessary
    - Running and testing the program
    - Debugging the program, if necessary
- Interpreted language workflow (see flowchart)
    - Writing down specifications
    - Creating the source code
    - Running the program in the interpreter
    - Reading the interpreter's output, determining if there is a syntax (language) error or the program finished executing
    - Editing the program to fix syntax errors
    - Testing the program (once it can run with no errors)
    - Debugging the program, if necessary
    - **Advantages**: Fewer steps between writing and executing, can be a faster cycle
    - **Disadvantages**: All errors happen when you run the program, no distinction between syntax errors (compile errors) and logic errors (bugs in running program)


#### Programming workflow 

<!-- TODO: title this figure -->

!["Flowchart demonstrating roles and tasks of a programmer, beta tester and user in the creation of programs."](img/flowchart)

- Integrated Development Environment (IDE)
    - Combines a text editor, compiler, file browser, debugger, and other tools
    - Helps you organize a programming project
    - Helps you write, compile, and test code in one place
    - Visual Studio terms:
        - Solution: An entire software project, including source code, metadata, input data files, etc.
        - "Build solution": Compile all of your code
        - "Start without debugging": Run the compiled code
        - Solution location: The folder (on your computer's file system) that contains the solution, meaning all your code and the information needed to compile and run it
