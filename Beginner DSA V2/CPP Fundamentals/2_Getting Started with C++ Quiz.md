<READING_WIDGET>
# Getting Started with C++ Quiz
</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does `#include <iostream>` do in a C++ program?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about what "io" in `iostream` stands for.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        It specifically includes the `iostream` (Input/Output Stream) library required for standard input (`cin`) and output (`cout`).
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It compiles the program into machine code.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It includes the standard input/output stream library, allowing you to use `cin` and `cout`.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It tells the compiler to optimize the code for speed.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It imports the entire C++ standard library.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basics, Includes
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which function is the mandatory entry point for every C++ program?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        The operating system looks for a very specific function name to start execution.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The operating system always looks for `int main()` to begin execution. Without it, the program cannot run.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `start()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `init()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `main()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `execute()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basics, Functions
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does `using namespace std;` prevent you from having to type repeatedly?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Namespaces are like last names for standard functions and objects.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Without it, you would have to write `std::cout` and `std::cin` every single time. It tells the compiler to assume you are using the standard (`std`) namespace.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `#include`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `std::`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int main()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basics, Namespaces
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the standard return value for `main()` to indicate that the program ran successfully?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        In operating systems, zero usually means "no errors".
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Returning `0` tells the operating system that the execution finished successfully without any errors.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `return 1;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `return -1;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `return true;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `return 0;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basics, Return Values
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Why do competitive programmers often use `#include <bits/stdc++.h>`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        It's a GCC-specific header file that acts as an umbrella for almost everything else.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        It's a GCC compiler extension that includes almost everything from `<iostream>` to `<vector>` to `<algorithm>`, which is perfect for the time-constrained environment of CP where saving typing time matters.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It makes the code run 10x faster.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It automatically solves compilation errors.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It includes almost all standard C++ libraries at once, saving typing time.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It prevents the program from using too much memory.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, CP Tricks, Includes
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What punctuation mark MUST end almost every standard statement in C++?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        It acts as a full stop for code sentences.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The semicolon `;` is the fundamental statement terminator in C++. Forgetting it is one of the most common compilation errors!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Colon `:`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Semicolon `;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Period `.`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Comma `,`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Syntax
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the fundamental difference between C and C++?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        C++ was originally named "C with Classes".
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        C++ was originally called "C with Classes" and brought Object-Oriented Programming (OOP) features to the standard C procedural language.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                C++ does not support loops.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                C is an Object-Oriented Language, while C++ is not.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                C++ is an extension of C that supports Object-Oriented Programming (Classes and Objects).
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                C is faster than C++ in every scenario.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, History, OOP
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which of the following is considered a single-line comment in C++?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        `/* */` is used for multi-line comments.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `//` is for single-line comments. Everything following `//` on that line is ignored by the compiler.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `/* comment */`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `// comment`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `# comment`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `<!-- comment -->`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Syntax, Comments
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which stage of building a C++ program actually combines your compiled code with the standard library code to create an executable?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        It "connects" different pieces of code together.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The Linker is responsible for linking your compiled object (`.o`) files with the external libraries to build the final executable (`.exe`).
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The Preprocessor
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The Compiler
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The Linker
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The Execution Engine
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Compilation Process
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **True or False: Does whitespace (spaces, tabs, newlines) affect how the C++ compiler understands your code?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        C++ relies on syntax punctuation (like semicolons and braces) rather than indentation to structure code.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        C++ is generally free-form. It relies on semicolons and braces for structure, meaning extra spaces or newlines don't affect logic. However, spaces are still needed to separate keywords (like `int main`), and whitespace inside quotes changes string content.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Yes, indentation is strictly enforced like in Python.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                No, C++ completely ignores whitespace in all scenarios.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Generally no; C++ is free-form and ignores whitespace except where it separates keywords or appears inside string literals.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Yes, putting two spaces instead of one causes a compiler error.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Syntax, Whitespace
    </MCQ_TAGS>
</MCQ_WIDGET>
