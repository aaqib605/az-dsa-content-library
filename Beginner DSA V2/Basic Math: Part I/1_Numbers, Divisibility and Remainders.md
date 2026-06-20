<VIDEO_WIDGET>

<VIDEO_ID>3470</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Numbers, Divisibility, and Remainders

Imagine it is currently Monday, and your friend asks you: _"What day of the week will it be exactly 100 days from now?"_

You _could_ pull out a calendar and painstakingly count 100 days forward one by one. But there's a much smarter way. You know that every 7 days, the days of the week perfectly reset. If you divide 100 by 7, you get 14 full weeks, with exactly 2 days left over.

Those 2 leftover days are the **remainder**. Since today is Monday, you just jump 2 days forward: Tuesday, _Wednesday_. It will be a Wednesday!

This idea of cyclical mapping and "wrapping around" is entirely driven by remainders. It is one of the most foundational math concepts you will use in programming. Let's dive in.

---

## 1. The Magic of Modulo (Remainders)

In school, you learned that when you divide 10 by 3, the quotient is 3 and the remainder is 1.
In programming, we rarely care about the quotient in these cyclical problems. We care about the remainder.

The **modulo operator** (`%`) gives you exactly that.

```cpp
int a = 10;
int b = 3;
cout << a % b << "\n"; // Prints 1
```

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/ce3a5b40-eb15-4e98-9612-33e85bd42269.png" alt="Modulo-Operator-1" style="max-width: 100%; height: auto;" identifier="az-img-upload">

### But why is this so useful?

The modulo operator is the ultimate tool for **wrapping around**. If you have an array of $N$ items, and you keep incrementing an index, it will eventually go out of bounds. But if you take `index % N`, it will perfectly loop back to 0 when it reaches $N$.

### Checking Divisibility

How do you know if a number $A$ is completely divisible by a number $B$?
If you can group all $A$ apples into boxes of $B$ with _nothing_ left over, then $A$ is divisible by $B$.

In code:

```cpp
if (A % B == 0) {
    cout << A << " is divisible by " << B << "\n";
}
```

---

## 2. Integer Division, Floor, and Ceil

While the modulo operator `%` gives us the remainder, the division operator `/` gives us the quotient. However, division in C++ has some quirks you must understand.

When you divide two integers in C++, the result is always an integer. The decimal part is **truncated** (chopped off).

```cpp
int a = 10;
int b = 3;
cout << a / b << "\n"; // Prints 3 (not 3.333...)
```

For positive numbers, this truncation acts exactly like a **floor** function (rounding down). But what if you want to round _up_ (ceiling)?

### The `<cmath>` Approach

C++ provides `floor()` and `ceil()` functions, but they work with floating-point numbers (`double`).

```cpp
#include <cmath>

// We must use 10.0 to force floating-point division
cout << ceil(10.0 / 3.0) << "\n";  // Prints 4
cout << floor(10.0 / 3.0) << "\n"; // Prints 3
```

_Socratic Question:_ Why not just use `ceil()` every time?
Because floating-point numbers can suffer from precision issues with very large numbers, leading to wrong answers (WA) in competitive programming. It's also slightly slower.

### The Pro Integer Math Trick for Ceiling

If you want the ceiling of $A / B$ (assuming $A$ and $B$ are strictly positive integers), you can do it completely within safe, fast integer math using this magical formula:

```cpp
int ceil_val = (A + B - 1) / B;
```

Let's trace it with $A = 10, B = 3$:
`(10 + 3 - 1) / 3` $\rightarrow$ `12 / 3` $\rightarrow$ `4`. It works perfectly!
This trick avoids floating-point inaccuracies entirely and is a staple in a competitive programmer's toolkit.

---

## 3. Odd and Even: Progressive Optimization

A classic first question: _Write a program to check if a number is even._

### The Naive Intuition

Some absolute beginners might try to repeatedly subtract 2 until they hit 0 or 1.

```cpp
// Time Complexity: O(N)
bool isEven(int N) {
    while (N > 1) {
        N -= 2;
    }
    return N == 0;
}
```

_Socratic Question:_ But what happens if $N$ is 1 billion? Your program will do 500 million subtractions! We need an $O(1)$ approach.

### The Standard Approach

As we just learned, an even number is simply any number divisible by 2.

```cpp
// Time Complexity: O(1)
bool isEven(int N) {
    return (N % 2 == 0);
}
```

---

## 4. Extracting Digits

One of the most common patterns in early DSA problems involves pulling numbers apart digit by digit (e.g., checking if a number is a palindrome, or summing its digits).

We use base-10 math for this:

- **`N % 10`**: Grabs the last digit.
- **`N / 10`**: Chops off the last digit.

Let's say $N = 456$.

1. `456 % 10 = 6` (We got the last digit!)
2. `456 / 10 = 45` (We removed the 6!)
3. `45 % 10 = 5` (Next digit!)
4. `45 / 10 = 4`
5. `4 % 10 = 4` (Last digit!)
6. `4 / 10 = 0` (We stop when $N$ reaches 0)

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/9df38876-18db-4e30-9e0d-2b6e2422d185.png" alt="Modulo-Operator-2" style="max-width: 100%; height: auto;" identifier="az-img-upload">

Here is how you write that in code:

```cpp
int N = 456;
int sum = 0;

while (N > 0) {
    int lastDigit = N % 10;
    sum += lastDigit;
    N = N / 10; // Prepare for the next iteration
}

cout << "Sum of digits: " << sum << "\n";
```

> 🚨 **The Negative Number Trap!**
> What happens if the problem gives you $N = -456$? The condition `N > 0` fails instantly, the loop never runs, and the sum returns `0`!
> Furthermore, if you just change it to `while (N != 0)`, the expression `-456 % 10` evaluates to `-6` in C++, which will completely break logic in problems like checking for palindromes or reversing integers.
> **The Fix:** Always take the absolute value first if the problem allows negative numbers: `N = abs(N);`

---

## 5. Edge Cases & "Gotchas"

Math seems simple until the compiler throws a mysterious error or your code gets a Time Limit Exceeded (TLE) verdict. Here are the traps.

### Trap 1: Division by Zero

What happens if you run `A % 0` or `A / 0`?
It doesn't return 0. It doesn't return negative infinity. **It crashes your program instantly with a Runtime Error.**
Always ensure your divisor `B` is never zero before performing modulo or division.

```cpp
if (B != 0) {
    int ans = A % B;
} else {
    // Handle the zero case
}
```

### Trap 2: Integer Overflow

When multiplying numbers before taking the modulo, you might exceed the 32-bit integer limit.
For example, $(10^5 \times 10^5) \% M$.
The result of $10^5 \times 10^5$ is $10^{10}$, which does not fit in a standard 32-bit `int` (limit is $\approx 2 \times 10^9$).

**The Fix:**
Always cast to `long long` _before_ the multiplication.

```cpp
// ❌ Dangerous (Overflows before modulo)
int result = (A * B) % M;

// ✅ Safe
int result = (1LL * A * B) % M;
```

</READING_WIDGET>
