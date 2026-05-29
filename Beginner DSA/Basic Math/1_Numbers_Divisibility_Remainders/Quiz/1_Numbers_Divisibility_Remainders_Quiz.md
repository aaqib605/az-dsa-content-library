---
title: "Numbers, Divisibility, and Remainders Quiz"
slug: "quiz-numbers-divisibility-remainders"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your knowledge on modulo arithmetic, integer division, and common math traps in competitive programming!"
---

# Numbers, Divisibility, and Remainders Quiz

Choose the correct answer for each question.

## Questions

### 1. What is the exact output of `-14 % 5` in C++?

A. `1`  
B. `-4`  
C. `4`  
D. `-1`  

### 2. You need to calculate the ceiling of $A / B$, where $A = 15$ and $B = 4$. Which of the following integer math formulas correctly computes the ceiling without using floating-point numbers?

A. `(A / B) + 1`  
B. `(A + B - 1) / B`  
C. `(A + B) / B`  
D. `(A / B) + (A % B)`  

### 3. Why is using `floor()` or `ceil()` from `<cmath>` sometimes dangerous in competitive programming?

A. They are significantly slower than integer operations  
B. They require importing a heavy library  
C. They convert integers to floating-point numbers, which can lead to precision loss and Wrong Answers (WA) for very large numbers  
D. They only work properly on negative numbers  

### 4. You are writing a `while` loop to extract the digits of a number $N$ and sum them up. If the problem states that $N$ can be negative (e.g., $N = -250$), what happens if your loop condition is `while(N > 0)`?

A. The loop runs normally, treating $N$ as a positive number  
B. The loop condition fails immediately and the loop never runs  
C. The loop runs infinitely  
D. The compiler throws a syntax error  

### 5. Consider the following C++ code designed to compute `(A * B) % M`:

```cpp
int A = 100000;
int B = 100000;
int M = 1000000007;
int ans = (A * B) % M;
```
What is the primary issue with this code?

A. `A * B` evaluates to $10^{10}$, which overflows a standard 32-bit integer *before* the modulo is applied  
B. The modulo operator `%` cannot be used with large numbers  
C. It will cause a division by zero error  
D. `ans` should be declared as a `double`  

## Answer Key

1. B - In C++, the modulo operator retains the sign of the dividend (the first number). Since `-14` is negative, the remainder is `-4`. To mathematically get a positive remainder, you would use `(-14 % 5 + 5) % 5` which gives `1`.
2. B - `(A + B - 1) / B` is the standard, safe integer math formula for calculating the ceiling of positive integers. `(15 + 4 - 1) / 4 = 18 / 4 = 4`.
3. C - The `double` data type has precision limits. When dealing with extremely large integers, casting them to floating-point numbers can cause precision loss, leading to incorrect calculations and WA. It's always safer to use pure integer math when possible.
4. B - If $N = -250$, the condition `N > 0` evaluates to `false` right from the start. The loop is entirely skipped, and your sum will remain `0`. Always use `N = abs(N)` before extracting digits if the number can be negative!
5. A - The multiplication `A * B` happens first. Since $10^{10}$ is larger than the maximum value of a 32-bit signed `int` ($\approx 2 \times 10^9$), it will overflow, resulting in garbage data before the modulo even executes. The safe way is to cast to a 64-bit integer first: `int ans = (1LL * A * B) % M;`.
