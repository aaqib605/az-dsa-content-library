# How to Check if a Solution Will Pass (The $10^8$ Rule)

You've read the problem, figured out the constraints, and designed an algorithm. But how do you know *for sure* if it will pass the Time Limit before you spend time coding it? 

Let's do some quick math!

## Understanding Constraints from the Problem Statement

Every good competitive programming or interview problem will have a **Constraints** section. It looks something like this:
- $1 \le T \le 100$ (Number of test cases)
- $1 \le N \le 10^5$ (Size of the array)
- $1 \le A[i] \le 10^9$ (Values inside the array)

**Rule #1:** When calculating time complexity, you only care about the variables that control the number of operations your code does (like $N$ or $T$). The actual values inside the array ($A[i]$) usually don't affect the time complexity (unless they are explicitly used as loop bounds).

## Estimating Allowed Operations (The $10^8$ Rule)

Here is the golden rule of modern competitive programming:
**A standard C++ program can execute roughly $10^8$ (100 million) basic operations in 1 second.**

*(Note: Python is slower, usually around $10^7$ operations per second, while Java is somewhere in between).*

If the problem has a Time Limit of 1.0 second, your goal is to keep the total number of worst-case operations strictly under $10^8$.

Let's say $N = 10^5$.
- If you write an **$O(N)$** algorithm: It takes $10^5$ operations. $10^5 < 10^8$, so it passes instantly!
- If you write an **$O(N \log N)$** algorithm: $\log_2(10^5) \approx 17$. So, $17 \times 10^5 = 1.7 \times 10^6$ operations. Still way less than $10^8$. It passes easily!
- If you write an **$O(N^2)$** algorithm: $(10^5)^2 = 10^{10}$ operations. $10^{10}$ is **100 times larger** than $10^8$. It will take about 100 seconds to run. **Time Limit Exceeded (TLE)!**

## Common Rough Limits for 1 Second in C++

To save you from doing math during a contest, memorize these rough limits for a 1-second time limit:

- **$O(N)$** will pass if $N \le 10^8$.
- **$O(N \log N)$** will pass if $N \le 10^6$ (or $5 \times 10^5$ to be safe).
- **$O(N^2)$** will pass if $N \le 10^4$ (ideally $3000$ to $5000$).
- **$O(N^3)$** will pass if $N \le 500$.
- **$O(2^N)$** will pass if $N \le 25$.
- **$O(N!)$** will pass if $N \le 11$.

## Considering the Number of Test Cases ($T$)

Many platforms (like CodeChef and Codeforces) group multiple test cases together into a single run. They will give you a variable $T$ representing the number of test cases.

If $T = 100$ and $N = 10^5$, and you write an $O(N)$ algorithm:
- Operations per test case: $10^5$
- Total operations: $T \times N = 100 \times 10^5 = 10^7$
- $10^7 < 10^8$, so it passes!

**Beware of the Trap!**
Sometimes $T$ is large (e.g., $10^5$) and $N$ is large (e.g., $10^5$). If you multiply them, $10^5 \times 10^5 = 10^{10}$, which would TLE even with an $O(N)$ algorithm! 

However, look closely at the problem description. You will often see a magical line: 
> *"The sum of $N$ over all test cases does not exceed $2 \cdot 10^5$."*

This means you don't need to multiply $T \times N$ for the worst case. The total sum of $N$ across the entire file is guaranteed to be small. As long as your complexity is $O(N)$ or $O(N \log N)$ per test case, the total time will just be proportional to the **Sum of $N$**, which will safely pass!
