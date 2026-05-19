---
title: "Functions Quiz"
slug: "functions-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on function syntax, parameters, return types, and variable scope."
---

# Functions Quiz

Test your understanding of organizing code into reusable blocks using Functions!

---

### 1. If a function is designed to just print something and does NOT return a value, what should its return type be?
A. `null`  
B. `empty`  
C. `void`  
D. `int`  

### 2. You write a helper function below `main()`. What will happen when you try to compile the code?
A. It compiles perfectly.  
B. The compiler throws an error because C++ reads from top to bottom and doesn't know the function exists yet.  
C. The program crashes at runtime.  
D. The function gets ignored.  

### 3. How do you fix the issue described in Question 2, allowing you to keep the function definition below `main()`?
A. You cannot fix it; it must be moved above `main()`.  
B. You use an `#include` statement.  
C. You place a **Function Prototype** (declaration) at the very top of the file before `main()`.  
D. You rename the function to `main2()`.  

### 4. What happens when a local variable inside a function has the exact same name as a global variable?
A. The compiler throws a "Duplicate Name" error.  
B. The two variables merge their values.  
C. The local variable **shadows** the global variable, meaning the function will only use the local version while inside that block.  
D. The global variable overwrites the local variable.  

### 5. Look at this code. What will be printed?
```cpp
void updateScore(int s) {
    s = s + 10;
}

int main() {
    int s = 50;
    updateScore(s);
    cout << s;
    return 0;
}
```
A. `60`  
B. `50`  
C. Compilation Error  
D. `0`  

### 6. Why did the code in Question 5 behave that way?
A. Because variables can only be modified inside `main()`.  
B. Because the function `updateScore` didn't have a `return` statement.  
C. Because standard parameters are passed **by value**, meaning the function only modified a temporary *photocopy* of `s`, leaving the original untouched.  
D. Because the variables had the same name.  

### 7. What is a "Function Prototype" in C++?
A. The very first function ever written in a program.  
B. A declaration at the top of the file (like `int add(int a, int b);`) that tells the compiler a function exists before its full definition is written.  
C. A function that calls itself recursively.  
D. A built-in standard library function.  

### 8. You have a `void` function. Can you still use the `return;` keyword inside it?
A. No, `void` functions can never have a return statement.  
B. Yes, but it must return 0 (e.g., `return 0;`).  
C. Yes, using a bare `return;` is perfectly valid to stop the function early.  
D. Yes, but it will print a warning.  

### 9. Which of the following is true about parameters passed to a standard C++ function?
A. They are always passed by reference by default.  
B. The function can rename the parameters to whatever it wants; they do not have to match the names in `main()`.  
C. You can pass a maximum of 5 parameters to a single function.  
D. Global variables must be passed as parameters to be accessed.  

### 10. What happens if you define a function inside another function (e.g., placing a function definition inside `main`)?
A. Standard C++ does not allow nested function definitions.  
B. It becomes a private function.  
C. It runs perfectly.  
D. It automatically becomes a lambda function.  

---

## Answer Key

1. **C** (`void` literally translates to "nothing", indicating the function does its job without giving data back).
2. **B** (C++ compilers are sequential. If they see a function call before the function exists, they panic).
3. **C** (A prototype like `void helper();` tells the compiler "trust me, the details for this function will appear later").
4. **C** (Variable Shadowing prioritizes the innermost, most local scope).
5. **B** (It prints `50` because the original variable in `main` was never modified).
6. **C** (By default, arguments are passed by value (photocopies). If you wanted to modify the original, you would need to pass it by reference using `&`).
7. **B** (Prototypes are essential if you want to organize your helper functions below `main()`).
8. **C** (A bare `return;` simply acts as an emergency exit for `void` functions).
9. **B** (The names of the parameters in the function definition are completely independent of the variable names you pass in from `main()`).
10. **A** (Unlike Python or JavaScript, standard C++ strictly forbids defining functions inside other functions. Use lambdas for that!).
