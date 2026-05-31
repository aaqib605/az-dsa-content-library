---
title: "Prime Numbers and Factorization Quiz"
slug: "quiz-prime-numbers-and-factorization"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your knowledge on prime checking, prime factorization, and the fundamental theorem of arithmetic."
---

# Prime Numbers and Factorization Quiz

Choose the correct answer for each question.

## Questions

### 1. By strict mathematical definition, what makes a number a "prime number"?

A. It is any odd number  
B. It has exactly two distinct factors: 1 and itself  
C. It cannot be divided by 2  
D. It has an odd number of factors  

### 2. What is the Worst-Case Time Complexity of the optimal algorithm to check if a number $N$ is prime?

A. $O(1)$  
B. $O(\log N)$  
C. $O(\sqrt{N})$  
D. $O(N)$  

### 3. If you run the optimal `isPrime(N)` checker on $N = 10^{12}$ (a massive even number), roughly how many times will the `for` loop actually execute before returning a result?

A. Exactly $1$ time  
B. Exactly $10^6$ times ($\sqrt{N}$)  
C. Exactly $10^{12}$ times  
D. It will cause an integer overflow error  

### 4. According to the Fundamental Theorem of Arithmetic, how can every single integer be uniquely represented?

A. As a sum of two perfect squares  
B. As a product of prime numbers raised to specific exponents ($P_1^{\alpha_1} \times P_2^{\alpha_2} \dots$)  
C. As a fraction of two odd numbers  
D. As a factorial of a smaller integer  

### 5. In the optimal Prime Factorization algorithm, why do we never accidentally extract a composite number (like 4 or 6) as a factor?

A. The compiler has a built-in list of primes it checks against  
B. We only loop through odd numbers  
C. Because all smaller prime factors (like 2 and 3) are completely divided out of $N$ *before* the loop ever reaches their composite multiples (like 4 or 6)  
D. Composite numbers don't actually exist in C++  

### 6. What is the Time Complexity of the optimal Prime Factorization algorithm?

A. $O(N)$  
B. $O(\log N)$  
C. $O(\sqrt{N})$  
D. $O(N \log N)$  

### 7. In the optimal $O(\sqrt{N})$ prime factorization loop, what does the inner `while (N % i == 0)` loop accomplish?

A. It prevents infinite loops  
B. It completely divides out the prime factor `i` from $N$ and counts its exponent $\alpha$  
C. It finds the next prime number to check  
D. It checks if the number is a perfect square  

### 8. What is the maximum number of prime factors a number $N$ can have that are strictly GREATER than $\sqrt{N}$?

A. $0$  
B. Exactly $1$  
C. $2$  
D. $\sqrt{N}$  

### 9. Why is the `if (N > 1)` check at the very end of the optimal Prime Factorization algorithm absolutely critical?

A. To prevent the program from returning negative numbers  
B. Because $N$ might evaluate to $0$, causing a division by zero error  
C. To catch the final, potentially leftover prime factor that is strictly greater than $\sqrt{N}$  
D. It is actually optional and only used for performance profiling  

### 10. While the theoretical upper bound for the total number of divisors of $N$ is $O(2\sqrt{N})$, what is a realistic maximum number of divisors you will encounter for $N \le 10^9$ in competitive programming?

A. $2 \times 10^9$  
B. Roughly $31,622$ (which is $\sqrt{10^9}$)  
C. Exactly $1,344$  
D. Only $2$  

## Answer Key

1. B - A prime number is strictly defined as a number greater than 1 that has exactly two factors: 1 and itself.
2. C - In the worst case (when $N$ is actually prime), the loop must check every single number from $2$ up to $\sqrt{N}$ to confirm there are no divisors.
3. A - The loop starts at $i = 2$. Since $10^{12}$ is even, $10^{12} \% 2 == 0$. The `if` condition is met instantly, and the function returns `false` on the very first iteration, making the average case incredibly fast!
4. B - The Fundamental Theorem of Arithmetic states that every integer greater than 1 is either prime or can be uniquely represented as the product of prime powers.
5. C - The algorithm continuously divides $N$ by a prime $P$ as long as possible. By the time the loop reaches $i = 4$, all factors of $2$ have already been permanently stripped out of $N$, making $N \% 4 == 0$ mathematically impossible!
6. C - Just like checking for primes, a number can have at most one prime factor greater than $\sqrt{N}$. Thus, we only ever need to loop up to the square root of $N$.
7. B - The inner `while` loop aggressively divides $N$ by the newly discovered prime factor `i` until it can't anymore. The number of times it divides perfectly is the exponent ($\alpha$) for that prime factor!
8. B - A number can have at most ONE prime factor strictly greater than its square root. If it had two, multiplying them together would result in a number strictly larger than $N$, which is mathematically impossible!
9. C - The loop stops at $\sqrt{N}$. If $N = 14$, the loop extracts $2$ and leaves $N = 7$. Since $7 > \sqrt{14}$, the loop terminates. The final `if (N > 1)` is required to capture that remaining prime factor!
10. C - While $O(2\sqrt{N})$ is the theoretical upper bound used for space complexity proofs, the actual maximum number of divisors for any number up to $10^9$ is only $1,344$. This proves that iterating over divisors will rarely cause a TLE.
