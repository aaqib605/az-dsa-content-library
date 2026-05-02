# Why We Prefer Higher Order Terms

Earlier, we briefly mentioned dropping "non-dominant" terms. Let's dive a little deeper into this. When we analyze an algorithm, we often get a mathematical equation that represents the total number of operations. For example:

$$T(N) = 3N^2 + 5N + 100$$

Here, we have three different terms:
- **$3N^2$** is the **Higher-Order Term** (it grows the fastest).
- **$5N$** and **$100$** are the **Lower-Order Terms** (they grow slower, or not at all).

In Big O notation, we completely ignore the lower-order terms and the coefficients (the numbers in front of the $N$). So, $T(N)$ simplifies cleanly to **$O(N^2)$**. But why do we do this?

## The Meaning of Lower-Order vs. Higher-Order

Think of it like spending money. 
- A **higher-order term** is like buying a house. It costs millions of rupees.
- A **lower-order term** is like buying a cup of chai on the way to the bank. It costs 20 rupees.

If you are calculating the total cost of buying the house, does the 20 rupees for the chai really matter? Not really! The cost of the house completely overshadows the cost of the tea.

## Why Lower-Order Terms Become Insignificant

The core philosophy of Big O notation is analyzing how an algorithm behaves as the input size ($N$) approaches **infinity**. Let's plug some numbers into our equation $T(N) = N^2 + N$ to see what happens as $N$ gets realistically large:

| Input Size ($N$) | Lower-Order Term ($N$) | Higher-Order Term ($N^2$) | Total Operations ($N^2 + N$) | % Contribution of $N^2$ |
| :--- | :--- | :--- | :--- | :--- |
| **10** | 10 | 100 | 110 | 90.9% |
| **100** | 100 | 10,000 | 10,100 | 99.0% |
| **1,000** | 1,000 | 1,000,000 | 1,001,000 | 99.9% |
| **100,000** | 100,000 | 10,000,000,000 | 10,000,100,000 | 99.999% |

Look closely at the bottom row. When $N = 100,000$, the $N^2$ term is doing 10 Billion operations! The extra 100,000 operations from the lower-order term barely make a dent in the total runtime. It's essentially a rounding error.

> 💡 **Interview Insight:** If you write an algorithm with two distinct steps—for example, first you sort the array $O(N \log N)$, and then you loop through it once $O(N)$—the total time is $O(N \log N + N)$. In an interview, you should immediately simplify this and confidently say, *"The overall time complexity is $O(N \log N)$ because the sorting step dominates the runtime."*

By focusing only on the higher-order terms, we strip away the mathematical clutter and focus entirely on the true bottleneck of our algorithm.