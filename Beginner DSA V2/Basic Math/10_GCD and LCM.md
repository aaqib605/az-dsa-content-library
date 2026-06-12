<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# GCD and LCM

Imagine you are hosting a party. You have $24$ slices of pizza and $15$ cans of soda. You want to create identical "party bags" containing both pizza and soda, using all your supplies with nothing left over. What is the maximum number of identical bags you can make? 
You are looking for the **Greatest Common Divisor (GCD)**! The answer is $3$ bags (each containing $8$ slices and $5$ sodas).

Now, imagine you have a bus that arrives at your stop every $12$ minutes, and a train that arrives every $18$ minutes. If they both arrive right now, how long do you have to wait until they arrive at the exact same time again? 
You are looking for the **Lowest Common Multiple (LCM)**! They will perfectly sync up in $36$ minutes.

These two concepts—GCD and LCM—are two sides of the same mathematical coin. While GCD helps us split things into the largest possible equal groups, LCM helps us find when repeating cycles finally align.

---

## 1. Finding the GCD: The Basics

The Greatest Common Divisor of two numbers $A$ and $B$ is the largest integer that divides both of them without leaving a remainder.

### The Naive Intuition (Brute Force)
The simplest way to find the GCD is to start from the smaller of the two numbers and count backward. The first number that divides both $A$ and $B$ is our GCD!

```cpp
// Time Complexity: O(min(A, B))
int naiveGCD(int a, int b) {
    int limit = min(a, b);
    for (int i = limit; i >= 1; i--) {
        if (a % i == 0 && b % i == 0) {
            return i;
        }
    }
    return 1; // 1 is always a common divisor
}
```
*Socratic Question:* What if $A = 10^9$ and $B = 10^9 - 1$? The loop will run a billion times just to return 1! How do we do this efficiently?

### The Built-In Approach: `gcd`
Writing an $O(\min(A, B))$ loop is far too slow for competitive programming. Thankfully, C++ has got you covered.

Starting from **C++17**, you don't need to manually write optimized GCD logic. You can simply include the `<numeric>` library and use the built-in `gcd()` function! 

```cpp
#include <numeric>
#include <iostream>
using namespace std;

int main() {
    // Time Complexity: O(log(min(A, B)))
    int ans = gcd(24, 15);
    cout << ans << "\n"; // Prints 3
}
```

> 💡 **CP Insight:** How fast is `gcd`? Under the hood, it uses an advanced mathematical technique called the *Euclidean Algorithm* (which we will learn how to write from scratch later). For now, all you need to know is that it runs in **$O(\log(\min(A, B)))$** time! It is blazing fast and handles massive numbers instantly.

---

## 2. LCM and The Magical Formula

The Lowest Common Multiple is the smallest number that is a multiple of both $A$ and $B$.
Instead of writing a loop to find the LCM, we use a profound mathematical relationship that links GCD and LCM together:

$$A \times B = \text{GCD}(A, B) \times \text{LCM}(A, B)$$

By rearranging this equation, we get an instant formula for LCM:

$$\text{LCM}(A, B) = \frac{A \times B}{\text{GCD}(A, B)}$$

> 💡 **CP Insight:** Just like GCD, C++17's `<numeric>` library provides a built-in `lcm(a, b)` function! However, knowing the formula under the hood is mandatory, because many problems require you to calculate LCMs of massive numbers manually using modular arithmetic.

---

## 3. Edge Cases & "Gotchas"

Even though using built-in functions is incredibly easy, implementing the LCM formula safely requires knowing C++ specific quirks.

### Trap 1: The LCM Overflow Disaster
Look at the formula: `(A * B) / gcd(A, B)`.
If $A = 100,000$ and $B = 100,000$, computing `A * B` first will result in $10^{10}$, which instantly overflows a standard 32-bit signed integer!

**The Fix:** Always divide *first*. Since the GCD is guaranteed to perfectly divide $A$, perform the division before the multiplication.

```cpp
// ❌ Dangerous: (A * B) overflows 32-bit int before division
int badLCM = (A * B) / gcd(A, B); 

// ❌ Still Dangerous: If GCD is 1, the multiplication still overflows!
long long stillBad = (A / gcd(A, B)) * B; 

// ✅ Bulletproof: Cast to 64-bit integer (1LL) during the math
long long goodLCM = (1LL * A / gcd(A, B)) * B; 
```

> 💡 **CP Must-Know:** When calculating LCM, **always divide first then multiply**. Furthermore, because LCMs grow exceptionally fast, you almost always need to store the final result in a `long long`.

### Trap 2: `gcd` vs `__gcd`
Depending on your coding environment, you might run into compiler issues using built-in functions.

> 💡 **CP Must-Know:** `gcd(A, B)` and `lcm(A, B)` are standard in **C++17** and newer. If you are coding on an older Online Judge that strictly uses C++14, `gcd` will cause a compilation error! In older C++ versions, competitive programmers use `__gcd(A, B)`, which is an internal GNU compiler function. Always check your environment's compiler version!

### Trap 3: Handling Zeros
What happens if a problem passes $0$ to the GCD function? Mathematically, $\text{GCD}(A, 0) = A$. 

> 💡 **CP Insight:** The built-in `gcd(A, 0)` safely returns $A$. This is a highly useful property when finding the GCD of an entire array, because you can initialize your tracking variable to $0$ (just like you initialize a sum variable to $0$) and run a simple loop!

</READING_WIDGET>
