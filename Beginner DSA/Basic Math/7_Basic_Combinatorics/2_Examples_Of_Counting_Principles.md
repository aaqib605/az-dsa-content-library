---
title: "Examples of Counting Principles"
slug: "examples-counting-principles"
track: "beginner-dsa"
level: "Beginner"
order: 2
status: "Draft"
duration: "13 min 13 sec"
videoStatus: "Published"
updatedAt: "2026-06-03"
description: "Apply the Multiplication and Addition principles to solve practical constraint-based combinatorial problems like palindromes and license plates."
---

# Examples of Counting Principles

In the previous module, we learned the Golden Rule of Counting: "AND" means multiply, "OR" means add. Let's see how these simple rules scale to solve complex, constraint-based combinatorial problems.

---

## 1. License Plates with Specific Constraints

**Problem:** 
Determine the number of possible license plates that can be created under the following conditions:
- The plate starts with exactly **two distinct** English letters.
- Followed by exactly **three distinct** digits.
- The first digit **cannot** be 0.

**Solution:**
We must select Letters **AND** Digits to form the full plate. Therefore, we will use the Multiplication Principle.

*Step 1: Choosing the Letters*
- The first letter has **26** possible choices (A-Z).
- The second letter must be distinct from the first, leaving exactly **25** choices.
- Total combinations for letters: $26 \times 25 = 650$

*Step 2: Choosing the Digits*
- The first digit has **9** possible choices (1-9), because 0 is excluded.
- The second digit can be any digit *except* the one just chosen. Since 0 is now allowed, we have $10 - 1 = \mathbf{9}$ choices.
- The third digit must be different from the first two, leaving $10 - 2 = \mathbf{8}$ choices.
- Total combinations for digits: $9 \times 9 \times 8 = 648$

*Step 3: Total License Plates*
Since we need letters **AND** digits, we multiply the two intermediate results:
$$650 \times 648 = \mathbf{421,200}$$

> 💡 **CP Insight:** When dealing with multiple constraint blocks (like letters then digits), solve each block completely independently first. Then, use the Multiplication Principle to join them together at the very end.

---

## 2. Palindromic Words

**Problem:** 
Calculate the total number of possible 5-letter palindromes that can be formed using standard English letters. Then, extend this formula to an $N$-letter palindrome.

**Solution:**
A palindrome reads the exact same forward as it does backward (e.g., "abcba"). 

*For a 5-letter palindrome:*
- The 1st and 5th letters are identical.
- The 2nd and 4th letters are identical.
- The 3rd letter is entirely unique.

Because the back-half of the word is just a mirror of the front-half, we only actually get to "choose" the first half of the word! The rest of the letters are forced choices (meaning we only have 1 choice for them).

- Choices for 1st letter: **26**
- Choices for 2nd letter: **26**
- Choices for 3rd letter: **26**
- Choices for 4th letter: **1** (Must exactly match 2nd letter)
- Choices for 5th letter: **1** (Must exactly match 1st letter)

Total combinations:
$$26 \times 26 \times 26 \times 1 \times 1 = 26^3 = \mathbf{17,576}$$

*Extension to an $N$-letter palindrome:*
If you look closely, the number of "free choices" we get is exactly half the length of the string, rounded up.

- **If N is even:** The first $\frac{N}{2}$ letters uniquely determine the entire palindrome. 
  Formula: $26^{\frac{N}{2}}$
- **If N is odd:** The first $\lfloor\frac{N}{2}\rfloor + 1$ letters determine the palindrome (including the unique middle character).
  Formula: $26^{\lfloor\frac{N}{2}\rfloor + 1}$

![A visual mapping of a 5-letter palindrome structure. Show 5 empty boxes. Box 1, 2, and 3 have '26 choices' written above them. Draw an arrow from Box 2 to Box 4, and Box 1 to Box 5, showing they are locked mirrors with '1 choice' written above them. Prompt: Create a diagram of 5 empty boxes representing a 5-letter palindrome. Show that the first three boxes have 26 independent choices, while the last two boxes are directly mirrored from the first two, demonstrating why only the first half contributes to the combination math.](../Images/palindrome_example.png)

> 💡 **CP Trick (Unifying Even and Odd):** 
> Instead of writing an `if/else` statement in your code for even and odd lengths, you can use a brilliant integer math trick. In C++ (where division automatically rounds down), the number of "free choices" is always exactly `(N + 1) / 2`. 
> - If $N=5$: `(5 + 1) / 2` $\rightarrow$ `6 / 2` = **3 choices**. 
> - If $N=6$: `(6 + 1) / 2` $\rightarrow$ `7 / 2` = **3 choices**. 
> The math unifies perfectly, meaning you can just calculate $26^{\frac{N + 1}{2}}$.

---

## 3. Numbers with Odd Digits & No Consecutive Repeats

**Problem:** 
Find the number of 10-digit numbers that can be formed using only odd digits (`1, 3, 5, 7, 9`) such that absolutely no two consecutive digits are the same. Extend this to an $N$-digit number.

**Solution:**
We have a pool of **5** available odd digits.

*Step-by-Step Construction:*
- The 1st digit has no restrictions, so it has **5** possible choices.
- The 2nd digit can be any odd digit *except* the one immediately preceding it. This leaves exactly **4** choices.
- The 3rd digit can be any odd digit *except* the 2nd digit. This again leaves exactly **4** choices.
- Every subsequent digit will permanently have exactly **4** choices.

*Total for a 10-digit number:*
$$5 \times 4 \times 4 \times 4 \dots \text{(9 times)}$$
$$= \mathbf{5 \times 4^9}$$

*Extension to an $N$-digit number:*
The logic remains identical. The very first slot gets 5 choices, and the remaining $(N-1)$ slots get exactly 4 choices each.
Formula:
$$\mathbf{5 \times 4^{N-1}}$$

---

## Video Explanation

[![Examples of Counting Principles](../Images/video-lecture-thumbnail.jpg)](https://maang.in/playlists/Counting-Principles-4805?resourceUrl=cs174-cp778-pl4805-rs11444&returnUrl=%5B%22%2Fcourses%2FMaths-for-Programming-174%3Ftab%3Dchapters%22%5D)
