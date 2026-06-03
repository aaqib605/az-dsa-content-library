---
title: "Progressions and Series Quiz"
slug: "quiz-progressions-and-series"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your mathematical foundation on APs, GPs, Series Summations, and the infamous C++ Modulo Division Trap!"
---

# Progressions and Series Quiz

Choose the correct answer for each question. Be careful with the modulo trap questions at the end!

## Questions

### 1. What is the 10th term of the following Arithmetic Progression: 5, 8, 11, 14, ...?
A. `32`  
B. `35`  
C. `29`  
D. `27`  

### 2. What is the sum of the first 20 terms of an Arithmetic Progression where the first term is 2 and the common difference is 5?
A. `980`  
B. `990`  
C. `1010`  
D. `198`  

### 3. What is the 6th term of the following Geometric Progression: 3, 6, 12, 24, ...?
A. `48`  
B. `72`  
C. `96`  
D. `192`  

### 4. What is the sum of the first 5 terms of a Geometric Progression where the first term is 4 and the common ratio is 3?
A. `242`  
B. `324`  
C. `484`  
D. `968`  

### 5. Under what strict mathematical condition is it possible to calculate the sum of an Infinite Geometric Progression?
A. The common ratio $r$ must be strictly positive ($r > 0$)  
B. The common ratio $r$ must be strictly between -1 and 1 ($-1 < r < 1$)  
C. The first term $a$ must be exactly 1  
D. The common difference must be greater than 1  

### 6. Calculate the sum of the infinite Geometric Progression: $8, 4, 2, 1, 0.5, \dots$
A. `15`  
B. `16`  
C. `32`  
D. `Infinity`  

### 7. Which of the following formulas mathematically computes the sum of the first $N$ squares ($1^2 + 2^2 + \dots + N^2$)?
A. $\frac{n(n + 1)}{2}$  
B. $\left[ \frac{n(n + 1)}{2} \right]^2$  
C. $\frac{n(n + 1)(2n + 1)}{6}$  
D. $N^2$  

### 8. Which of the following formulas mathematically computes the sum of the first $N$ cubes ($1^3 + 2^3 + \dots + N^3$)?
A. $\frac{n(n + 1)}{2}$  
B. $\left[ \frac{n(n + 1)}{2} \right]^2$  
C. $\frac{n(n + 1)(2n + 1)}{6}$  
D. $N^3$  

### 9. In competitive programming, when calculating the sum of an AP modulo $10^9+7$, why is writing `((n * (n+1)) % MOD) / 2` mathematically dangerous?
A. Because `n * (n+1)` will always overflow a 64-bit integer, regardless of $N$.  
B. Because dividing by 2 *after* applying the modulo can result in truncating an odd remainder in C++, silently destroying the true mathematical answer.  
C. Because the modulo operator (`%`) does not work on negative numbers.  
D. Because $10^9+7$ is not a prime number.  

### 10. What is the *only* mathematically safe way to divide by 2 when evaluating $\frac{n(n+1)}{2}$ under a prime modulo like $10^9+7$ in C++?
A. Cast all variables to `double` before dividing by 2.  
B. Divide $n$ by 2 first, then multiply by $(n+1)$.  
C. Multiply the numerator by the Modular Multiplicative Inverse of 2 modulo $10^9+7$ (using Fermat's Little Theorem).  
D. Add $10^9+7$ to the numerator before dividing by 2.  

---

## Answer Key

1. **A** - The $N$-th term formula is $T_n = a + (n - 1)d$. Here $a=5, d=3, n=10$. $T_{10} = 5 + (9 \times 3) = 5 + 27 = 32$.
2. **B** - The AP Sum formula is $S_n = \frac{n}{2} [2a + (n - 1)d]$. Here $n=20, a=2, d=5$. $S_{20} = \frac{20}{2} [2(2) + (19 \times 5)] = 10 \times [4 + 95] = 10 \times 99 = 990$.
3. **C** - The GP $N$-th term formula is $T_n = a \times r^{n-1}$. Here $a=3, r=2, n=6$. $T_6 = 3 \times 2^5 = 3 \times 32 = 96$.
4. **C** - The GP Sum formula is $S_n = a \times \frac{r^n - 1}{r - 1}$. Here $a=4, r=3, n=5$. $S_5 = 4 \times \frac{3^5 - 1}{3 - 1} = 4 \times \frac{243 - 1}{2} = 4 \times \frac{242}{2} = 4 \times 121 = 484$.
5. **B** - An infinite GP sum only mathematically converges to a finite number if the sequence is shrinking. This strictly happens when $-1 < r < 1$. If $r \ge 1$, it explodes to infinity.
6. **B** - The infinite GP Sum formula is $S_\infty = \frac{a}{1 - r}$. Here $a=8, r=0.5$. $S_\infty = \frac{8}{1 - 0.5} = \frac{8}{0.5} = 16$.
7. **C** - This is the standard mathematical identity for the sum of the first $N$ squares. Knowing this prevents running an $O(N)$ loop in CP!
8. **B** - The sum of the first $N$ cubes is beautifully identical to the *square* of the sum of the first $N$ natural numbers!
9. **B** - The C++ Modulo Division Trap! If `(n * (n+1)) % MOD` evaluates to an odd number (like 27), performing `/ 2` on it natively in C++ truncates it to 13, irreversibly destroying your answer.
10. **C** - As we learned in the Modular Arithmetic module, division mathematically does not exist in modulo logic. You must convert the division into multiplication by finding the fraction's Modular Multiplicative Inverse using Fermat's Little Theorem!
