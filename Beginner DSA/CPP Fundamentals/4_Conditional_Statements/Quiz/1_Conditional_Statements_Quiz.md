---
title: "Conditional Statements Quiz"
slug: "conditional-statements-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on if-else logic, logical operators, short-circuiting, and switch cases."
---

# Conditional Statements Quiz

Test your understanding of branching logic and decision-making in C++!

---

### 1. Which operator is used to check if two values are EXACTLY equal?
A. `=`  
B. `==`  
C. `===`  
D. `!=`  

### 2. In a sequence of `if ... else if ... else`, how many blocks of code will be executed if multiple conditions are technically true?
A. All of them.  
B. Only the first one that evaluates to true.  
C. Only the last one that evaluates to true.  
D. It will cause a compilation error.  

### 3. You need to check if a number `x` is between 10 and 20 (inclusive). Which is the correct syntax?
A. `if (10 <= x <= 20)`  
B. `if (x >= 10 and 20)`  
C. `if (x >= 10 && x <= 20)`  
D. `if (x >= 10 || x <= 20)`  

### 4. What does the Logical NOT operator `!` do?
A. It subtracts 1 from a variable.  
B. It flips `true` to `false`, and `false` to `true`.  
C. It checks if a variable is empty.  
D. It ends the program immediately.  

### 5. What is "Short-Circuiting" in C++?
A. When an infinite loop crashes the program.  
B. When the program skips the second half of an `&&` or `||` check because the overall result is already determined by the first half.  
C. When `if` statements are nested too deeply.  
D. A compilation error caused by missing curly braces.  

### 6. In a `switch` statement, what happens if you forget to put a `break;` at the end of a `case`?
A. The switch statement fails to compile.  
B. It gracefully exits the switch block automatically.  
C. "Fall-through" occurs: it will continue executing the code in the subsequent cases until it hits a `break` or the switch ends.  
D. It causes an infinite loop.  

### 7. What is the equivalent Ternary Operator for the following logic: 
```cpp
int max_val;
if (a > b) max_val = a;
else max_val = b;
```
A. `int max_val = a > b ? a : b;`  
B. `int max_val = a > b : a ? b;`  
C. `int max_val = (a > b) == a || b;`  
D. `int max_val = ? a > b : a : b;`  

### 8. What is the scope of a variable declared inside an `if` block?
A. It is accessible anywhere in the program.  
B. It is accessible anywhere within the `main()` function.  
C. It is destroyed as soon as the `if` block ends and cannot be accessed outside.  
D. It overwrites any global variables automatically.  

### 9. Which of the following conditional checks will fail to compile?
A. `if (a == 5 || b == 10)`  
B. `if (a == 5 && b == 10)`  
C. `if (a => 5)`  
D. `if (a >= 5)`  

### 10. If you have an `if` statement without curly braces `{}`, how many lines of code belong to that `if` statement?
A. All indented lines directly below it.  
B. Exactly 1 line (the very next statement).  
C. Until a blank line is reached.  
D. It will cause a compilation error.  

---

## Answer Key

1. **B** (`=` assigns a value, `==` compares them).
2. **B** (An `if-else` ladder guarantees that *only* the first true block is executed, entirely skipping the rest).
3. **C** (Chaining operators like `10 <= x <= 20` is syntactically legal but a massive logical trap in C++. C++ will evaluate `10 <= x` first into a `0` or `1`, and then check if that `0` or `1` is `<= 20`, which is always true! You must explicitly separate the conditions using the logical AND `&&` operator).
4. **B** (`!` simply reverses the boolean value. `!true` is `false`).
5. **B** (For example, in `A && B`, if `A` is false, C++ knows the whole expression is false and completely skips evaluating `B`).
6. **C** (Fall-through is a notorious bug. Always remember your `break;` statements in a switch!).
7. **A** (The ternary format is `condition ? true_value : false_value;`).
8. **C** (Variables declared inside curly braces `{}` are strictly local to that block).
9. **C** (`=>` is not a valid C++ operator. The greater-than-or-equal operator is strictly `>=`).
10. **B** (Omitting curly braces makes only the single next statement part of the `if`. This is a common source of bugs!).
