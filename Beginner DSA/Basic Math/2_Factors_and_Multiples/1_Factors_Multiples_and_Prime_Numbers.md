---
title: "Factors, Multiples, and Prime Numbers"
slug: "factors-multiples-prime-numbers"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
videoStatus: "Not Published"
updatedAt: "2026-05-31"
description: "Discover the properties of factors and multiples, how to optimize algorithms from O(N) to O(sqrt(N)), and the elegant secrets of prime numbers."
---

# Factors, Multiples, and Prime Numbers

Imagine you are a teacher with 24 students, and you want to arrange their desks into a perfect rectangular grid. There can be no empty gaps in the rows. 

How many different ways can you arrange them?
You could do 1 long row of 24. 
You could do 2 rows of 12. 
You could do 3 rows of 8.
You could do 4 rows of 6.

By doing this, you've just discovered the **factors** of 24. A factor is any number that perfectly divides another number without leaving a remainder. Conversely, 24 is a **multiple** of 3, 4, 6, 8, etc.

Understanding factors and multiples is the gateway to number theory. It shows up in cryptography, logic puzzles, and countless interview problems.

---

## 1. Finding All Factors

Let's write a program to find and print all the factors of a given number $N$.

### The Naive Intuition (Brute Force)
The simplest way is to test every single number from $1$ up to $N$. If $N \% i == 0$, then $i$ is a factor.

```cpp
// Time Complexity: O(N)
void printFactors(int N) {
    for (int i = 1; i <= N; i++) {
        if (N % i == 0) {
            cout << i << " ";
        }
    }
}
```
*Socratic Question:* What if $N = 10^{12}$? 
The $O(N)$ loop will take roughly 1000 seconds to run! In competitive programming, you only have 1 or 2 seconds. We need a massive optimization.

### The Optimal Approach $O(\sqrt{N})$
Here is a profound mathematical property: **Factors always exist in pairs.**

Let's look at the factors of 36:
- $1 \times 36 = 36$
- $2 \times 18 = 36$
- $3 \times 12 = 36$
- $4 \times 9 = 36$
- $6 \times 6 = 36$

Notice a pattern? Once we pass the square root of 36 (which is 6), the pairs just reverse! $9 \times 4$ is the exact same pair as $4 \times 9$. 
This means **we only ever need to check up to the square root of $N$**. Whenever we find a factor $i$, its partner is simply $N / i$.

![A U-shaped curve diagram mapping the pairs of factors for 36. An arrow goes down the left side (1, 2, 3, 4) and up the right side (36, 18, 12, 9), hitting the bottom exactly at 6 (the square root), demonstrating visually that searching past the square root is redundant.](../Images/u_shaped_curve_diagram_for_factors.png)

Here is the optimized code:

```cpp
// Time Complexity: O(sqrt(N))
void printFactorsOptimal(int N) {
    for (int i = 1; i * i <= N; i++) {
        if (N % i == 0) {
            cout << i << " ";
            
            // Check if the partner is different from 'i'
            if (i != N / i) {
                cout << N / i << " ";
            }
        }
    }
}
```

> 💡 **Must-Know Insight:** In the code above, we added the condition `if (i != N / i)`. Why? Because if $N$ is a perfect square (like 36), the partner of 6 is 6. If we didn't add this check, we would print `6` twice!

> 🚨 **The "Unsorted" Trap!**
> Did you notice what happens if we run the optimal code for $N = 36$? 
> The output will be: `1 36 2 18 3 12 4 9 6`. 
> The naive $O(N)$ approach gave us the factors in perfectly sorted order, but the $O(\sqrt{N})$ approach bounces back and forth between small and large factors! If a problem asks you to find the "$K^{th}$ factor of $N$", you cannot just count iterations in this loop. 
> **The Fix:** Push the factors into a `std::vector` inside the loop, and then call `sort(v.begin(), v.end())` at the end!

---

## 2. Mathematical Insights: The Perfect Square Anomaly

Factors give us one of the coolest properties in mathematics, which frequently appears in logic puzzles.

> 💡 **CP Insight:** Only perfect squares have an **odd** number of factors. Every other number has an **even** number of factors.

Think about it: factors always come in pairs (which means they come in 2s, an even number). The *only* time you don't get two distinct numbers is when $i = N / i$ (e.g., $6 \times 6 = 36$). That single, un-paired number in the middle makes the total count odd!

**Why does this matter?** 
Have you ever heard the classic interview puzzle: *"There are 100 closed doors and 100 people. Person 1 toggles every door, Person 2 toggles every 2nd door, Person 3 toggles every 3rd door... Which doors are left open at the end?"*
A door is toggled once for every factor its number has. To end up open, it must be toggled an *odd* number of times. Therefore, only the perfect square doors (1, 4, 9, 16...) remain open!

---

## 3. Generating Multiples

While finding factors is about dividing, generating multiples is about multiplying. 
If a problem asks you to find the first $K$ multiples of $N$, you just use a basic loop.

```cpp
// Time Complexity: O(K)
void printMultiples(int N, int K) {
    for (int i = 1; i <= K; i++) {
        cout << N * i << " ";
    }
}
```
Multiples are extremely straightforward. However, they are the foundation for a much bigger concept: the **Lowest Common Multiple (LCM)**, which we will explore later!

---

## 4. Application: Checking for Prime Numbers

Since we just learned the optimal way to find factors, we are perfectly equipped to check if a number is **prime**.

By definition, a prime number is a number strictly greater than 1 that has **exactly two factors**: $1$ and itself. 

How do we check if $N$ is prime? We don't even need to count all the factors. We just need to know if we can find *any* factor between $2$ and $\sqrt{N}$. If we find even a single one, the number is definitely not prime!

```cpp
// Time Complexity: O(sqrt(N)) in the worst case (if N is prime)
// Best Case: O(1) if N is divisible by 2 immediately
bool isPrime(int N) {
    if (N <= 1) return false; // 0 and 1 are not prime
    
    for (int i = 2; i * i <= N; i++) {
        if (N % i == 0) {
            return false; // We found a factor! It's not prime.
        }
    }
    return true; // No factors found between 2 and sqrt(N), it must be prime.
}
```

> 💡 **CP Insight:** Notice how we start our loop at `2` and return `false` the exact moment we find a divisor. If $N$ is an even number like $1,000,000$, the loop runs exactly *once* and stops. This makes our prime checker blazingly fast in the average case!

---

## 5. Edge Cases & "Gotchas"

Even in a beautifully optimized $O(\sqrt{N})$ algorithm, there is a hidden trap that causes many candidates to fail.

### Trap 1: The Integer Overflow in the Loop Condition

Look at our optimal loop condition again:
`for (int i = 1; i * i <= N; i++)`

If $N$ is very large (say, $N$ is near the 32-bit maximum of $2.14 \times 10^9$), then `i` will eventually reach $46,341$. What happens when the loop evaluates `i * i`?
$46,341 \times 46,341 = 2,147,488,281$.
This number strictly exceeds the 32-bit signed integer limit, causing an overflow! The condition will evaluate to garbage negative numbers, and your loop will run infinitely.

**The Fix:**
You have two safe options.

1. **Use `long long` for `i`:** `for (long long i = 1; i * i <= N; i++)`
2. **Use safe division instead of multiplication:** `for (int i = 1; i <= N / i; i++)` 

> 💡 **CP Must-Know:** Using `i <= N / i` is completely immune to overflow because you are dividing, not multiplying! It is considered the safest and most robust way to write an $O(\sqrt{N})$ loop in C++.

### Trap 2: Precision Loss and Performance Hit with `sqrt()`
You might be tempted to use the built-in math function: `for (int i = 1; i <= sqrt(N); i++)`.

This is a bad idea for two reasons:
1. **Precision Loss:** `sqrt()` operates on floating-point numbers (`double`). For extremely large 64-bit integers (`long long`), floating-point precision loss can cause `sqrt()` to return a number that is slightly off, making you skip a factor entirely.
2. **Performance Hit:** If you put `sqrt(N)` directly in the loop condition, it gets recalculated on *every single iteration*! Since calculating a square root takes $O(\log N)$ time at the CPU level, your blazingly fast loop just became noticeably slower. 

Always stick to safe, extremely fast integer math: `i <= N / i`.

---

## Let's Practice!

Ready to put these insights to the test? Master these concepts by solving this curated progression of problems:

- **[Prime Check AZ101](https://maang.in/problems/Prime-Check-AZ101-323)**
- **[Number of Divisors AZ101](https://maang.in/problems/Number-of-Divisors-AZ101-322)**
- **[Number of Common Factors](https://leetcode.com/problems/number-of-common-factors/)**
- **[Valid Perfect Square](https://leetcode.com/problems/valid-perfect-square/)**
- **[Perfect Number](https://leetcode.com/problems/perfect-number/)** 
- **[Three Divisors](https://leetcode.com/problems/three-divisors/)**
- **[The kth Factor of n](https://leetcode.com/problems/the-kth-factor-of-n/)**
- **[Bulb Switcher](https://leetcode.com/problems/bulb-switcher/description/)**

---

## Video Explanation

[![Factors, Multiples, and Prime Numbers](../Images/video-lecture-thumbnail.jpg)]()
