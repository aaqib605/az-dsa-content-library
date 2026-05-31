---
title: "GCD and LCM Quiz"
slug: "gcd-and-lcm-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your understanding of the Greatest Common Divisor, Lowest Common Multiple, and how to compute them safely in C++."
---

# GCD and LCM Quiz

Choose the correct answer for each question.

## Questions

### 1. What does the Greatest Common Divisor (GCD) of two numbers $A$ and $B$ represent?

A. The smallest number that both $A$ and $B$ divide evenly into  
B. The largest integer that divides both $A$ and $B$ without leaving a remainder  
C. The product of $A$ and $B$  
D. The remainder when $A$ is divided by $B$  

### 2. If a problem asks you to find when two cycles of different lengths will perfectly align again, which concept do you need?

A. Greatest Common Divisor (GCD)  
B. Lowest Common Multiple (LCM)  
C. Modular Exponentiation  
D. Prime Factorization  

### 3. What is the Time Complexity of the naive (brute-force) approach to finding the GCD by counting down from the minimum of $A$ and $B$?

A. $O(1)$  
B. $O(\log(\min(A, B)))$  
C. $O(\min(A, B))$  
D. $O(A \times B)$  

### 4. What is the Time Complexity of the incredibly fast `std::gcd(a, b)` function provided in C++?

A. $O(1)$  
B. $O(\log(\min(A, B)))$  
C. $O(\sqrt{N})$  
D. $O(\min(A, B))$  

### 5. Which of the following is the correct mathematical relationship between two numbers, their GCD, and their LCM?

A. $\text{LCM}(A, B) = \text{GCD}(A, B) \times A \times B$  
B. $A + B = \text{GCD}(A, B) + \text{LCM}(A, B)$  
C. $A \times B = \text{GCD}(A, B) \times \text{LCM}(A, B)$  
D. $\text{LCM}(A, B) = \frac{\text{GCD}(A, B)}{A \times B}$  

### 6. You need to calculate the LCM of $A = 100,000$ and $B = 100,000$. Why is writing `int ans = (A * B) / std::gcd(A, B);` a disastrous idea?

A. `std::gcd` does not accept large numbers  
B. $A \times B$ evaluates to $10^{10}$, which instantly overflows a 32-bit signed integer *before* the division happens  
C. It causes a division by zero error  
D. It returns the GCD instead of the LCM  

### 7. Even if you divide first, what happens if $A$ and $B$ are extremely large co-prime numbers (e.g., $A = 99,991$ and $B = 99,989$) and you write `long long ans = (A / std::gcd(A, B)) * B;`?

A. The code perfectly computes the LCM and stores it safely  
B. `std::gcd` crashes because the numbers are co-prime  
C. The multiplication still evaluates as a 32-bit integer math operation and overflows before being assigned to the `long long` variable  
D. It returns $1$  

### 8. What is the bulletproof, safest way to calculate the LCM of two integers $A$ and $B$ in C++ to avoid all overflow traps?

A. `long long lcm = (A * B) / std::gcd(A, B);`  
B. `int lcm = (A / std::gcd(A, B)) * B;`  
C. `long long lcm = (1LL * A / std::gcd(A, B)) * B;`  
D. `long long lcm = std::gcd(A, B) / (A * B);`  

### 9. Which header file must you include to use the standard `std::gcd` and `std::lcm` functions in C++17?

A. `<math.h>`  
B. `<numeric>`  
C. `<algorithm>`  
D. `<utility>`  

### 10. Mathematically and programmatically, what does `std::gcd(A, 0)` evaluate to?

A. $0$  
B. $1$  
C. $A$  
D. It throws a Runtime Error (Division by Zero)  

## Answer Key

1. B - The Greatest Common Divisor is the largest possible integer that divides perfectly into both numbers.
2. B - The Lowest Common Multiple is used to find when repeating cycles of different lengths (like orbits or gears) sync up or align.
3. C - A naive loop starts at the smaller of the two numbers and counts down by $1$. In the worst case (when the GCD is $1$), it will run exactly $\min(A, B)$ times.
4. B - Under the hood, `std::gcd` uses the Euclidean Algorithm, which aggressively reduces the numbers using modulo arithmetic, achieving a lightning-fast $O(\log(\min(A, B)))$ Time Complexity.
5. C - This fundamental theorem connects the two concepts: the product of two numbers is exactly equal to the product of their GCD and LCM.
6. B - Multiplying $A$ and $B$ first causes the value to exceed $2.14 \times 10^9$ (the 32-bit limit), resulting in garbage negative numbers before the division even gets a chance to shrink it down.
7. C - Because both $A$ and $B$ are 32-bit `int`s, C++ performs the multiplication as a 32-bit `int` by default. Even though you are assigning it to a `long long`, the overflow *already happened* during the multiplication!
8. C - By explicitly casting the math to a 64-bit integer using `1LL * A`, you force C++ to evaluate the entire equation safely in 64-bit space, perfectly avoiding the overflow. And dividing first ensures intermediate values stay as small as possible.
9. B - Both `std::gcd` and `std::lcm` were introduced in C++17 and are located inside the `<numeric>` library.
10. C - The Greatest Common Divisor of any non-zero number $A$ and $0$ is $A$. This makes it incredibly convenient to initialize an accumulator variable to $0$ when computing the GCD of an entire array!
