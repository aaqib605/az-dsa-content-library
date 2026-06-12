<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Getting Started with C++

Welcome to the world of C++! If you are getting started with Competitive Programming or Data Structures and Algorithms, C++ is the most popular language of choice because of its blazing fast speed and a powerful standard library. 

In this module, we will explore the absolute basics of a C++ program, understand what each line means, and learn how to run your code on an Online Judge.

---

## The Basic Structure of a C++ Program

Whenever you write a C++ program, you will use a standard template. Think of it as a boilerplate that you will write before solving any problem.

Here is what it looks like:

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    // Your code goes here
    
    return 0;
}
```

Let's break this down line by line!

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/f99d4be3-40ca-4d82-9bf1-40aa56237082.png" alt="Code Indentation" style="max-width: 100%; height: auto;" identifier="az-img-upload">

### 1. `#include <bits/stdc++.h>`
This is the **header file**. In C++, you need to import certain files to use built-in features (like taking input or printing output). 
- Normally, you would include specific libraries like `<iostream>` for input/output, `<vector>` for vectors, or `<string>` for strings.
- However, in competitive programming, we use `<bits/stdc++.h>`. This single file includes almost *every* standard library you will ever need! It saves you from memorizing and writing multiple `#include` statements.

> 💡 **Interview Insight:** While `<bits/stdc++.h>` is a lifesaver in competitive programming, **do not** use it in software development interviews or production code. It increases compilation time and isn't standard across all compilers. Use specific headers like `<iostream>` instead when doing real-world development!

### 2. `using namespace std;`
The C++ Standard Library contains many functions and objects (like `cin` and `cout`). These are organized into a "namespace" called `std` (short for standard).
If we don't include this line, we would have to type `std::` before everything, like this: `std::cout << "Hello";`. 
Writing `using namespace std;` tells the compiler to use this namespace by default, keeping our code clean and fast to type.

### 3. `int main()`
This is the starting point of your program. Whenever you run a C++ file, the computer looks for the `main()` function and starts executing the code inside it, line by line. Every C++ program **must** have a `main()` function!

### 4. `return 0;`
This tells the operating system, "Hey, the program finished running successfully!" Returning `0` implies there were no errors. If your program crashes, it might return a non-zero value.

---

## Syntax Rules: Semicolons, Braces, and Indentation

To write code that the compiler can understand, you need to follow certain grammatical rules of C++.

### Semicolons `;`
In English, a sentence ends with a full stop (`.`). In C++, a statement ends with a semicolon (`;`). 
If you forget a semicolon, the compiler will throw a fit and give you a **Compilation Error (CE)**!

```cpp
int a = 5; // Correct
int b = 10 // Error! Missing semicolon
```

### Curly Braces `{ }`
Curly braces group multiple lines of code together into a "block." You will see them used with functions (like `int main()`), loops, and conditions. Always make sure every opening brace `{` has a matching closing brace `}`.

### Indentation
Unlike Python, C++ doesn't strictly care about spaces or indentation. The compiler will run your code even if it's entirely on one line! 
However, **human readability is crucial**. Proper indentation makes your code structured and helps you spot bugs easily.

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/1397efdd-b5e9-4f8e-8aef-fd35a80e703c.png" alt="Messy vs. Clean Code" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## Comments: Leaving Notes in Code

Comments are notes you leave for yourself or others. The C++ compiler completely ignores them.

- **Single-line comment:** Use `//` to comment out everything until the end of the line.
- **Multi-line comment:** Use `/*` to start and `*/` to end a comment block.

```cpp
// This is a single-line comment

/* 
This is a 
multi-line comment 
*/
```

> 💡 **Pro Tip:** Don't write comments explaining *what* your code is doing if it's obvious. Use comments to explain *why* you are doing it. In competitive programming, quickly commenting out broken pieces of code is a great debugging strategy.

---

## How Online Judge (OJ) Programs Run

When you solve a problem on a platform like Codeforces, LeetCode, or HackerRank, your code is tested by an **Online Judge (OJ)**.

Here is the exact lifecycle of your submission:

1. **Compilation:** The OJ tries to translate your C++ code into machine language. If you missed a semicolon, it gives a **Compilation Error (CE)**.
2. **Execution:** If it compiles, the OJ runs your program and feeds it secret test cases (Inputs). 
3. **Evaluation:** The OJ captures the output your program prints and compares it exactly with the expected correct answer.
    - If it matches perfectly: **Accepted (AC) ✅**
    - If it's different: **Wrong Answer (WA) ❌**
    - If your code takes too long: **Time Limit Exceeded (TLE) ⏳**
    - If your code crashes: **Runtime Error (RE) ⚠️**

### A crucial note on Output Formatting!
Online Judges are incredibly strict. If the expected output is `Yes`, and you print `yes` or `Yes ` (with an extra space), you will get a **Wrong Answer**. Always print exactly what is asked!

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/ee511530-4b5a-4d53-916a-5407f28a877f.png" alt="OJ Flowchart" style="max-width: 100%; height: auto;" identifier="az-img-upload">

</READING_WIDGET>