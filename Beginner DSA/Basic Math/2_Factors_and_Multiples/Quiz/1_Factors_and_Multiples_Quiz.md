---
title: "Factors and Multiples Quiz"
slug: "quiz-factors-and-multiples"
track: "beginner-dsa"
level: "Beginner"
order: 2
status: "Draft"
description: "Test your knowledge on finding factors optimally, the perfect square anomaly, and common overflow traps."
---

# Factors and Multiples Quiz

Choose the correct answer for each question.

## Questions

### 1. What is the fundamental mathematical property that allows us to find all factors of $N$ in $O(\sqrt{N})$ time?

A. Every number is a multiple of 2  
B. Factors always exist in pairs  
C. You can divide $N$ by 10 to reduce the search space  
D. Multiples grow exponentially  

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

### 4. In the classic "100 Doors" interview puzzle, where the $i$-th person toggles every $i$-th door, why do only the perfect square doors remain open at the end?

A. Perfect squares are easier to calculate  
B. Perfect squares have an EVEN number of factors, so they get toggled an even number of times  
C. Perfect squares have an ODD number of factors, meaning they get toggled an odd number of times and end up open  
D. They don't remain open; all doors end up closed  

### 5. What is the Time Complexity to generate and print the first $K$ multiples of a given number $N$?

A. $O(N)$  
B. $O(\sqrt{N})$  
C. $O(K)$  
D. $O(N \times K)$  

### 6. You write a loop with the condition `for (int i = 1; i * i <= N; i++)`. If $N$ is near the 32-bit maximum ($2.14 \times 10^9$), what dangerous trap will you fall into when $i$ reaches $46,341$?

A. Division by zero  
B. Infinite loop due to floating-point precision loss  
C. Integer overflow, because $46,341^2$ exceeds the 32-bit signed integer limit  
D. The compiler will refuse to run the code  

### 7. What is the safest and most robust way to write the condition for an $O(\sqrt{N})$ factor-finding loop in C++ to completely avoid overflow?

A. `for (int i = 1; i <= sqrt(N); i++)`  
B. `for (int i = 1; i * i <= N; i++)`  
C. `for (long double i = 1; i <= N; i++)`  
D. `for (int i = 1; i <= N / i; i++)`  

### 8. Why is placing the `sqrt(N)` function directly inside the loop condition (e.g., `i <= sqrt(N)`) a bad idea for performance?

A. It requires importing a heavy Python library  
B. `sqrt()` is recalculated on every single iteration, which takes $O(\log N)$ time and drastically slows down the loop  
C. It limits the loop to exactly 10 iterations  
D. It forces the loop to run in $O(N^2)$ time  

### 9. Why should you avoid using the `<cmath>` `sqrt()` function when finding factors of extremely large 64-bit integers (`long long`)?

A. `sqrt()` does not exist in C++  
B. It operates on floating-point numbers (`double`), which can suffer from precision loss and cause you to skip factors entirely  
C. It returns a string instead of an integer  
D. It automatically rounds up to the nearest perfect square  

### 10. You need to find the $K^{th}$ factor of a given number $N$. Why can't you just stop the optimal $O(\sqrt{N})$ loop on the $K^{th}$ iteration and print the answer?

A. The $O(\sqrt{N})$ loop prints the factors out of order (in pairs), so the $K^{th}$ iteration does not correspond to the true $K^{th}$ smallest factor  
B. The loop doesn't check numbers larger than $K$  
C. The loop will throw an integer overflow error  
D. It is mathematically impossible to find the $K^{th}$ factor without $O(N)$ time  

## Answer Key

1. B - Factors always exist in pairs (e.g., for 36, $4 \times 9$). Because of this, once you reach the square root, the pairs simply reverse. You only need to search up to $\sqrt{N}$ to find all unique pairs!
2. C - The $O(\sqrt{N})$ approach prints factors in pairs as it finds them (`i` and `N/i`). So it prints 1 and 36, then 2 and 18, then 3 and 12, etc., resulting in an unsorted output.
3. B - Only perfect squares have an odd number of factors because their square root is paired with itself (e.g., $7 \times 7 = 49$). Every non-perfect square has an even number of factors.
4. C - A door is toggled once for every factor its number has. To end up open, it must be toggled an odd number of times. Since only perfect squares have an odd number of factors, they are the only ones left open!
5. C - To find the first $K$ multiples of $N$, you simply run a loop from $1$ to $K$ multiplying $N \times i$. This takes exactly $O(K)$ time.
6. C - $46,341 \times 46,341 = 2,147,488,281$, which strictly exceeds the maximum value of a 32-bit signed integer ($2,147,483,647$). This causes an overflow that turns the condition into garbage negative numbers.
7. D - `i <= N / i` is completely immune to integer overflow because it uses division instead of multiplication. It is the gold standard for writing $O(\sqrt{N})$ loops in C++.
8. B - Calculating a square root at the CPU level takes $O(\log N)$ time. Placing `sqrt(N)` in the condition causes it to recalculate on every step, noticeably slowing down a loop that is supposed to be fast.
9. B - `sqrt()` works with `double`. For extremely large numbers near the 64-bit limit, the floating-point precision can be slightly off, returning a wrong root and causing you to skip factors entirely.
10. A - The output of the optimal approach bounces between small and large factors (the "Unsorted Trap"). To find the true $K^{th}$ factor, you must push all factors into a vector and sort them first!
