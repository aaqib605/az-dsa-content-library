<VIDEO_WIDGET>

<VIDEO_ID>3431</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Complete Guide to Time Complexity in Problem Solving

Time complexity is not just something you calculate after writing code. It helps you choose the right approach before you begin, avoid Time Limit Exceeded errors, and understand what kind of solution the problem constraints are pointing toward.

## Table of Contents

1. [Time Complexity in Problem Solving](#time-complexity-in-problem-solving)
2. [How to Check if a Solution Will Pass](#how-to-check-if-a-solution-will-pass)

---

## Time Complexity in Problem Solving

Understanding Time Complexity isn't just about passing interviews. It's your secret weapon for solving algorithmic problems. It acts as a compass, guiding you toward the correct approach before you even write a single line of code.

### How Time Complexity Helps Choose the Right Approach

Imagine you are given a problem on a platform like CodeChef, Codeforces, or LeetCode. You read the description, and an idea pops into your head. Should you start coding immediately? **No!**

Before coding, you should:

1. **Estimate the time complexity** of your idea.
2. **Look at the constraints** of the problem, such as $N \le 10^5$.
3. Check if your complexity will pass within the standard time limit, usually 1 or 2 seconds.

If your idea is too slow, you just saved yourself 30 minutes of writing and debugging useless code. You can immediately pivot to thinking about a faster approach.

### Brute Force vs. Optimized Solution

When tackling a hard problem, it's highly recommended to start with the **Brute Force** solution.

- **Brute Force:** The most obvious, straightforward way to solve a problem, usually involving checking every possible answer. It's often $O(N^2)$ or $O(2^N)$.

Why start here? Because it ensures you actually understand the problem. Once you have the brute force approach, you can analyze its time complexity, find the bottleneck, and optimize it.

**Example: Finding a pair of numbers in an array that sum to a target.**

1. **Brute Force ($O(N^2)$):** Check every single pair using nested loops. If $N = 10^5$, this will Time Limit Exceed (TLE).
2. **Optimized ($O(N \log N)$):** Sort the array first, then use the Two-Pointer technique.
3. **Highly Optimized ($O(N)$):** Use a Hash Map to store numbers you've seen and look up the required difference in $O(1)$ time.

By knowing your complexities, you can clearly communicate this progression to an interviewer.

### Connecting Constraints with Expected Complexity

This is the ultimate competitive programming cheat code!

Modern CPUs can perform roughly $10^8$ operations per second. By looking at the maximum value of $N$ in the problem description, you can reverse-engineer the time complexity the author expects you to use.

Here is a table you should memorize:

| Problem Constraint     | Expected Time Complexity   | Possible Algorithms                              |
| :--------------------- | :------------------------- | :----------------------------------------------- |
| $N \le 10$ to $20$     | $O(N!)$, $O(2^N)$          | Backtracking, Permutations, Bitmasking           |
| $N \le 100$            | $O(N^3)$, $O(N^4)$         | 3D/4D Dynamic Programming, Matrix Multiplication |
| $N \le 1,000$          | $O(N^2)$                   | Nested Loops, 2D Dynamic Programming             |
| $N \le 10^5$ to $10^6$ | $O(N \log N)$, $O(N)$      | Sorting, Binary Search, Two Pointers, Hash Maps  |
| $N \le 10^9$           | $O(\sqrt{N})$, $O(\log N)$ | Prime Factorization, Binary Search on Answer     |
| $N \le 10^{18}$        | $O(\log N)$, $O(1)$        | Fast Exponentiation, Math formulas               |

**How to use this table:**

If a problem says $N \le 10^5$, and you are trying to write an $O(N^2)$ solution, stop and rethink. $10^5 \times 10^5 = 10^{10}$, which is way more than $10^8$. It will definitely TLE. You need an $O(N)$ or $O(N \log N)$ algorithm.

> **Interview Insight:** If an interviewer asks you to optimize an $O(N^2)$ solution, your brain should immediately jump to the techniques that yield $O(N \log N)$, like sorting or binary search, or $O(N)$, like hash maps or two pointers.

---

## How to Check if a Solution Will Pass

You've read the problem, figured out the constraints, and designed an algorithm. But how do you know if it will pass the time limit before you spend time coding it?

Let's do some quick math.

### Understanding Constraints from the Problem Statement

Every good competitive programming or interview problem will have a **Constraints** section. It looks something like this:

- $1 \le T \le 100$ (Number of test cases)
- $1 \le N \le 10^5$ (Size of the array)
- $1 \le A[i] \le 10^9$ (Values inside the array)

**Rule #1:** When calculating time complexity, you only care about the variables that control the number of operations your code does, like $N$ or $T$. The actual values inside the array ($A[i]$) usually don't affect the time complexity unless they are explicitly used as loop bounds.

### Estimating Allowed Operations: The $10^8$ Rule

Here is the golden rule of modern competitive programming:

**A standard C++ program can execute roughly $10^8$ (100 million) basic operations in 1 second.**

Python is slower, usually around $10^7$ operations per second, while Java is somewhere in between.

If the problem has a time limit of 1.0 second, your goal is to keep the total number of worst-case operations strictly under $10^8$.

Let's say $N = 10^5$.

- If you write an **$O(N)$** algorithm: It takes $10^5$ operations. $10^5 < 10^8$, so it passes instantly.
- If you write an **$O(N \log N)$** algorithm: $\log_2(10^5) \approx 17$. So, $17 \times 10^5 = 1.7 \times 10^6$ operations. Still way less than $10^8$. It passes easily.
- If you write an **$O(N^2)$** algorithm: $(10^5)^2 = 10^{10}$ operations. $10^{10}$ is **100 times larger** than $10^8$. It will take about 100 seconds to run. **Time Limit Exceeded (TLE)!**

### Common Rough Limits for 1 Second in C++

To save yourself from doing math during a contest, memorize these rough limits for a 1-second time limit:

- **$O(N)$** will pass if $N \le 10^8$.
- **$O(N \log N)$** will pass if $N \le 10^6$, or $5 \times 10^5$ to be safe.
- **$O(N^2)$** will pass if $N \le 10^4$, ideally $3000$ to $5000$.
- **$O(N^3)$** will pass if $N \le 500$.
- **$O(2^N)$** will pass if $N \le 25$.
- **$O(N!)$** will pass if $N \le 11$.

### Considering the Number of Test Cases ($T$)

Many platforms, like CodeChef and Codeforces, group multiple test cases together into a single run. They will give you a variable $T$ representing the number of test cases.

If $T = 100$ and $N = 10^5$, and you write an $O(N)$ algorithm:

- Operations per test case: $10^5$
- Total operations: $T \times N = 100 \times 10^5 = 10^7$
- $10^7 < 10^8$, so it passes.

**Beware of the Trap!**

Sometimes $T$ is large, such as $10^5$, and $N$ is also large, such as $10^5$. If you multiply them, $10^5 \times 10^5 = 10^{10}$, which would TLE even with an $O(N)$ algorithm.

However, look closely at the problem description. You will often see a line like this:

> _"The sum of $N$ over all test cases does not exceed $2 \cdot 10^5$."_

This means you don't need to multiply $T \times N$ for the worst case. The total sum of $N$ across the entire file is guaranteed to be small. As long as your complexity is $O(N)$ or $O(N \log N)$ per test case, the total time will just be proportional to the **sum of $N$**, which will safely pass.

</READING_WIDGET>
