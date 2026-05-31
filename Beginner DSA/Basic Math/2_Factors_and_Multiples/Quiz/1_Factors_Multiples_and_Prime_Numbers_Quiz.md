---
title: "Factors, Multiples, and Prime Numbers Quiz"
slug: "quiz-factors-multiples-prime-numbers"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your knowledge on finding factors optimally, the perfect square anomaly, and common traps in number theory."
---

# Factors, Multiples, and Prime Numbers Quiz

Choose the correct answer for each question.

## Questions

### 1. What is the fundamental mathematical property that allows us to find all factors of $N$ in $O(\sqrt{N})$ time?

A. Every number is a multiple of 2  
B. Factors always exist in pairs  
C. Prime numbers only have one factor  
D. You can divide $N$ by 10 to reduce the search space  

### 2. If you use the optimal $O(\sqrt{N})$ loop to print the factors of $36$, which of the following perfectly describes the output sequence before any sorting?

A. `1 2 3 4 6 9 12 18 36`  
B. `36 18 12 9 6 4 3 2 1`  
C. `1 36 2 18 3 12 4 9 6`  
D. `6 6 4 9 3 12 2 18 1 36`  

### 3. Which of the following numbers will have an ODD number of total factors?

A. $24$  
B. $49$  
C. $50$  
D. $1000$  

### 4. You write a loop with the condition `for (int i = 1; i * i <= N; i++)`. If $N = 2.14 \times 10^9$ (near the 32-bit maximum), what dangerous trap will you fall into when $i$ reaches $46,341$?

A. Division by zero  
B. Infinite loop due to floating-point precision loss  
C. Integer overflow, because $46,341^2$ exceeds the 32-bit signed integer limit  
D. The compiler will refuse to run the code  

### 5. What is the safest and most robust way to write the condition for an $O(\sqrt{N})$ factor-finding loop in C++ to completely avoid overflow?

A. `for (int i = 1; i <= sqrt(N); i++)`  
B. `for (int i = 1; i * i <= N; i++)`  
C. `for (long double i = 1; i <= N; i++)`  
D. `for (int i = 1; i <= N / i; i++)`  

### 6. Why is placing the `sqrt(N)` function directly inside the loop condition (e.g., `i <= sqrt(N)`) a bad idea for performance?

A. It requires importing a heavy Python library  
B. `sqrt()` is recalculated on every single iteration, which takes $O(\log N)$ time and slows down the loop  
C. It limits the loop to exactly 10 iterations  
D. It forces the loop to run in $O(N^2)$ time  

### 7. Why should you avoid using the `<cmath>` `sqrt()` function when dealing with extremely large 64-bit integers (`long long`)?

A. `sqrt()` does not exist in C++  
B. It returns a string instead of an integer  
C. It operates on floating-point numbers (`double`), which can suffer from precision loss and skip factors entirely  
D. It automatically rounds up to the nearest perfect square  

### 8. What is the Worst-Case Time Complexity of the optimal algorithm to check if a number $N$ is prime?

A. $O(1)$  
B. $O(\log N)$  
C. $O(\sqrt{N})$  
D. $O(N)$  

### 9. If you run our optimal `isPrime(N)` checker on $N = 1,000,000$, how many times will the `for` loop actually execute before returning a result?

A. Exactly $1$ time  
B. Exactly $1,000$ times  
C. Exactly $1,000,000$ times  
D. It won't run at all  

### 10. You need to find the $K^{th}$ factor of a given number $N$. Why can't you just stop the optimal $O(\sqrt{N})$ loop on the $K^{th}$ iteration and print the answer?

A. The $O(\sqrt{N})$ loop prints the factors out of order (in pairs), so the $K^{th}$ iteration does not correspond to the true $K^{th}$ smallest factor  
B. The loop doesn't check numbers larger than $K$  
C. The loop will throw an integer overflow error  
D. It is mathematically impossible to find the $K^{th}$ factor without $O(N)$ time  

## Answer Key

1. B - Factors always exist in pairs (e.g., for 36, $4 \times 9$). Because of this, once you reach the square root, the pairs simply reverse. You only need to search up to $\sqrt{N}$ to find all unique pairs!
2. C - The $O(\sqrt{N})$ approach prints factors in pairs as it finds them (`i` and `N/i`). So it prints 1 and 36, then 2 and 18, then 3 and 12, etc., resulting in an unsorted output.
3. B - Only perfect squares have an odd number of factors because their square root is paired with itself (e.g., $7 \times 7 = 49$). Every non-perfect square has an even number of factors.
4. C - $46,341 \times 46,341 = 2,147,488,281$, which strictly exceeds the maximum value of a 32-bit signed integer ($2,147,483,647$). This causes an overflow that turns the condition into garbage negative numbers.
5. D - `i <= N / i` is completely immune to integer overflow because it uses division instead of multiplication. It is the gold standard for writing $O(\sqrt{N})$ loops in C++.
6. B - Calculating a square root at the CPU level takes $O(\log N)$ time. Placing `sqrt(N)` in the condition causes it to recalculate on every step, noticeably slowing down a loop that is supposed to be fast.
7. C - `sqrt()` works with `double`. For extremely large numbers near the 64-bit limit, the floating-point precision can be slightly off, returning a wrong root and causing you to skip factors entirely.
8. C - In the worst case (when $N$ is actually prime), the loop has to check every single number from $2$ up to $\sqrt{N}$ to confirm there are no divisors. Thus, the Worst-Case Time Complexity is $O(\sqrt{N})$.
9. A - The loop starts at $i = 2$. Since $1,000,000 \% 2 == 0$, the `if` condition is met instantly, and the function returns `false` on the very first iteration. This makes the average case exceptionally fast.
10. A - The output of the optimal approach bounces between small and large factors (the "Unsorted Trap"). To find the true $K^{th}$ factor, you must push all factors into a vector and sort them first!
