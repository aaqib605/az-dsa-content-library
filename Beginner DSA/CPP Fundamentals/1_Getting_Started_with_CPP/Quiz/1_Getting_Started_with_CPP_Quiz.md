---
title: "Getting Started with C++ Quiz"
slug: "getting-started-with-cpp-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on C++ boilerplate, the main function, and compilation!"
---

# Getting Started with C++ Quiz

Test your understanding of the absolute basics of C++.

---

### 1. What does `#include <iostream>` do in a C++ program?
A. It compiles the program into machine code.  
B. It includes the standard input/output stream library, allowing you to use `cin` and `cout`.  
C. It tells the compiler to optimize the code for speed.  
D. It imports the entire C++ standard library.  

### 2. Which function is the mandatory entry point for every C++ program?
A. `start()`  
B. `init()`  
C. `main()`  
D. `execute()`  

### 3. What does `using namespace std;` prevent you from having to type repeatedly?
A. `#include`  
B. `std::`  
C. `int main()`  
D. `;`  

### 4. What is the standard return value for `main()` to indicate that the program ran successfully?
A. `return 1;`  
B. `return -1;`  
C. `return true;`  
D. `return 0;`  

### 5. Why do competitive programmers often use `#include <bits/stdc++.h>`?
A. It makes the code run 10x faster.  
B. It automatically solves compilation errors.  
C. It includes almost all standard C++ libraries at once, saving typing time.  
D. It prevents the program from using too much memory.  

### 6. What punctuation mark MUST end almost every standard statement in C++?
A. Colon `:`  
B. Semicolon `;`  
C. Period `.`  
D. Comma `,`  

### 7. What is the fundamental difference between C and C++?
A. C++ does not support loops.  
B. C is an Object-Oriented Language, while C++ is not.  
C. C++ is an extension of C that supports Object-Oriented Programming (Classes and Objects).  
D. C is faster than C++ in every scenario.  

### 8. Which of the following is considered a single-line comment in C++?
A. `/* comment */`  
B. `// comment`  
C. `# comment`  
D. `<!-- comment -->`  

### 9. Which stage of building a C++ program actually combines your compiled code with the standard library code to create an executable?
A. The Preprocessor  
B. The Compiler  
C. The Linker  
D. The Execution Engine  

### 10. True or False: Does whitespace (spaces, tabs, newlines) affect how the C++ compiler understands your code?
A. Yes, indentation is strictly enforced like in Python.  
B. No, C++ completely ignores whitespace in all scenarios.  
C. Generally no; C++ is free-form and ignores whitespace except where it separates keywords or appears inside string literals.  
D. Yes, putting two spaces instead of one causes a compiler error.  

---

## Answer Key

1. **B** (It specifically includes the `iostream` library required for standard input and output).
2. **C** (The operating system always looks for `int main()` to begin execution).
3. **B** (Without it, you would have to write `std::cout` and `std::cin` every single time).
4. **D** (Returning `0` tells the operating system that the execution finished without any errors).
5. **C** (It's a GCC extension that includes everything from `<iostream>` to `<vector>` to `<algorithm>`, perfect for the time-constrained environment of CP).
6. **B** (The semicolon `;` is the fundamental statement terminator in C++).
7. **C** (C++ was originally called "C with Classes" and brought OOP features to standard C).
8. **B** (`//` is for single-line comments, while `/* */` is for multi-line).
9. **C** (The Linker is responsible for linking your compiled `.o` files with the external libraries to build the final `.exe`).
10. **C** (C++ relies on semicolons and braces for structure, meaning extra spaces or newlines don't matter, though spaces are still needed to separate keywords like `int` and `main`, and whitespace inside quotes changes string content).
