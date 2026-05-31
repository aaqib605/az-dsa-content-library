---
title: "Prime Numbers and Factorization"
slug: "prime-numbers-and-factorization"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: "16 min 13 sec"
videoStatus: "Published"
updatedAt: "2026-05-31"
description: "Learn how to efficiently check for prime numbers in O(sqrt(N)) time and break numbers down into their prime factors using the Fundamental Theorem of Arithmetic."
---

# Prime Numbers and Factorization

Prime numbers are the atoms of mathematics. Every single integer in existence is either a prime number itself, or it can be uniquely created by multiplying prime numbers together. 

In computer science, prime numbers form the absolute foundation of cryptography (like RSA algorithms that keep your passwords safe) and hashing.

In this module, we will explore two fundamental problems:
1. **Prime Checking:** Is $N$ a prime number?
2. **Prime Factorization:** What prime numbers multiply together to create $N$?

---

## 1. Checking for Prime Numbers

By definition, a prime number is a number strictly greater than 1 that has **exactly two factors**: $1$ and itself.

If we want to know if $N$ is prime, we just need to see if it has any other divisors. But how far do we need to check? 

In our *Factors and Multiples* module, we learned that factors always exist in pairs, and the largest pair we need to check is bounded by $\sqrt{N}$. If we can't find a factor by the time we reach the square root, we will *never* find one!

```cpp
// Time Complexity: O(sqrt(N)) in the worst case
// Best Case: O(1) if N is divisible by 2 immediately
bool isPrime(long long N) {
    if (N <= 1) return false; // 0 and 1 are not prime
    
    // We check up to sqrt(N). Using i <= N / i avoids integer overflow.
    for (long long i = 2; i <= N / i; i++) {
        if (N % i == 0) {
            return false; // We found a factor! It's definitely not prime.
        }
    }
    return true; // No factors found, it must be prime.
}
```

> 💡 **CP Insight:** Notice how we start our loop at `2` and return `false` the exact moment we find a divisor. If $N$ is a massive even number like $10^{12}$, the loop runs exactly *once* and stops. This makes our prime checker blazingly fast in the average case!

---

## 2. Prime Factorization

Instead of just checking if a number is prime, what if we want to break it down into its core prime components? 

### The Fundamental Theorem of Arithmetic
Any number $N$ can be uniquely represented as the product of prime numbers raised to specific powers:

$$N = P_1^{\alpha_1} \times P_2^{\alpha_2} \times P_3^{\alpha_3} \times \dots$$

Where:
- $P_i$ are distinct prime numbers.
- $\alpha_i$ are their respective exponents (how many times that prime divides $N$).

For example, if $N = 60$, its prime factorization is $2^2 \times 3^1 \times 5^1$.

### The Optimal Approach $O(\sqrt{N})$
We can use the exact same $\sqrt{N}$ trick to factorize. We loop through potential prime factors up to $\sqrt{N}$. If $i$ perfectly divides $N$, we continuously divide $N$ by $i$ to count its exponent $\alpha$. 

To represent the formula programmatically, we will store each prime factor and its exponent as a pair (`pair<long long, long long>`).

```cpp
#include <vector>
#include <iostream>
using namespace std;

// Time Complexity: O(sqrt(N))
vector<pair<long long, long long>> primeFactorization(long long N) {
    vector<pair<long long, long long>> factors;
    
    for (long long i = 2; i <= N / i; i++) {
        if (N % i == 0) {
            long long count = 0;
            // Keep dividing out the prime factor to find its exponent
            while (N % i == 0) {
                count++;
                N /= i;
            }
            factors.push_back({i, count});
        }
    }
    
    // If N is still greater than 1, the remaining N is itself a prime!
    if (N > 1) {
        factors.push_back({N, 1});
    }
    
    return factors;
}
```

> 💡 **CP Must-Know:** The `if (N > 1)` check at the very end is the most commonly forgotten line of code by beginners. Why is it needed? A number can have **at most one** prime factor strictly greater than $\sqrt{N}$. If you try to factorize $N = 14$, the loop will extract $2$, leaving $N = 7$. Because $7$ is greater than $\sqrt{14}$, the loop stops! Without the final check, you would completely miss the prime factor $7$.

---

## 3. Mathematical Insights: Number of Divisors

Because factors exist in pairs (one strictly $\le \sqrt{N}$ and one strictly $\ge \sqrt{N}$), we can definitively establish an upper bound on how many total divisors a number can have.

> 💡 **Interview Insight:** What is the maximum number of divisors a number $N$ can have? Because we only check up to $\sqrt{N}$, there can be at most $\sqrt{N}$ pairs. Therefore, a number $N$ can have **at most $O(2\sqrt{N})$ divisors**. In practice, it is much smaller! For example, for $N \le 10^9$, the maximum number of divisors any number has is only **1,344**. This proves that iterating over divisors later on will rarely cause a Time Limit Exceeded (TLE) error.

---

## Let's Practice!

Ready to put these insights to the test? 
- **[Prime Check AZ101](https://maang.in/problems/Prime-Check-AZ101-323)**
- **[Largest Prime Factor](https://projecteuler.net/problem=3)**
- **[Ugly Number](https://leetcode.com/problems/ugly-number/)**
- **[Largest Prime Factor](https://www.hackerrank.com/contests/projecteuler/challenges/euler003/problem)**

---

## Video Explanation

[![Prime Numbers and Factorization](../Images/video-lecture-thumbnail.jpg)](https://maang.in/playlists/Number-Theory-Foundations-4821?resourceUrl=cs174-cp783-pl4821-rs8010&returnUrl=%5B%22%2Fcourses%2FMaths-for-Programming-174%3Ftab%3Dchapters%22%5D)
