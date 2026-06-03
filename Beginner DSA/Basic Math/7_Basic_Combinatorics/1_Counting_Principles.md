---
title: "Counting Principles"
slug: "counting-principles"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: "4 min 58 sec"
videoStatus: "Published"
updatedAt: "2026-06-03"
description: "Master the foundational counting principles—the Golden Rule of 'AND' vs 'OR'—to solve complex combinatorial problems."
---

# Introduction to Counting Principles

Combinatorics is the mathematics of counting. When calculating permutations, combinations, or probability, we often face massive numbers of possible outcomes. Instead of manually listing every outcome, we rely on two fundamental counting tools: the **Multiplication Principle** and the **Addition Principle**.

Before diving into complex formulas, you must master the Golden Rule of Counting.

---

## The Golden Rule of Counting

When dissecting a problem statement, pay extremely close attention to the phrasing of choices. The entire foundation of combinatorics boils down to two simple conjunctions:

- If the word **"OR"** appears between choices, we **add** the possibilities.
- If the word **"AND"** appears between choices, we **multiply** the possibilities.

> 💡 **CP Insight:** The biggest mistake beginners make in combinatorics is randomly guessing whether to multiply or add intermediate results. If you can clearly articulate your logic using the words "AND" or "OR" out loud, the math writes itself!

---

## 1. Multiplication Principle (The "AND" Rule)

The Multiplication Principle states:
*"If one event can occur in $m$ ways and a second event can occur in $n$ ways after the first event has occurred, then the two events can occur together in $m \times n$ ways."*

### Example: Selecting a Boy AND a Girl
**Scenario:** A class consists of 18 girls and 15 boys. The teacher needs to select exactly one girl **AND** exactly one boy to represent the class in a competition.

**Calculation:**
- The number of ways to select the girl: 18
- The number of ways to select the boy: 15

Since the teacher must make *both* choices (one girl **AND** one boy), we multiply the possibilities:
$$18 \times 15 = 270 \text{ ways}$$

**Why?**
Imagine making a tree diagram. For the 1st selected girl, there are 15 different boy partners. For the 2nd selected girl, there are 15 different boy partners, and so on. Since there are 18 girls, the total combinations are exactly $18 \times 15$.

![A visual tree diagram showing a small example (e.g., 2 girls and 3 boys) branching out to prove why multiplication (2 x 3 = 6) perfectly maps all combinations. Prompt: Create a tree diagram with a root node branching into 2 'Girl' nodes. From each Girl node, branch out into 3 'Boy' nodes, visually demonstrating why 2 choices AND 3 choices result in exactly 6 total combinations.](../Images/multiplication_principle.png)

---

## 2. Addition Principle (The "OR" Rule)

The Addition Principle states:
*"If one event can occur in $m$ ways and a mutually exclusive second event can occur in $n$ ways, then the first event **OR** the second event can occur in $m + n$ ways."*

### Example: Selecting a Boy OR a Girl
**Scenario:** A class consists of 18 girls and 15 boys. The teacher needs to select exactly one student (either a girl **OR** a boy) to be the class monitor.

**Calculation:**
- The number of ways to select a girl: 18
- The number of ways to select a boy: 15

Since the teacher is choosing a girl **OR** a boy (and a student cannot be both), these events are mutually exclusive. We add the possibilities:
$$18 + 15 = 33 \text{ ways}$$

**Why?**
There are simply 33 distinct individuals in the room. Picking exactly one person from a pool of 33 means you have 33 total options.

> 💡 **Mathematical Prerequisite:** The addition rule only works perfectly if the sets have no common outcomes (they are mutually exclusive). If there is an overlap, you will have to use the Principle of Inclusion-Exclusion (which we will cover later in the curriculum).

---

## Let's Practice!

Now that you understand the mathematical difference between "AND" (Multiply) and "OR" (Add), it's time to put it to the test!

- **[Bit Strings](https://cses.fi/problemset/task/1617)**
- **[Lucky Numbers](https://codeforces.com/problemset/problem/630/C)**
- **[Pashmak and Flowers](https://codeforces.com/problemset/problem/459/B)**
- **[Dictionary](https://codeforces.com/problemset/problem/1674/B)**

---

## Video Explanation

[![Counting Principles](../Images/video-lecture-thumbnail.jpg)](https://maang.in/playlists/Counting-Principles-4805?resourceUrl=cs174-cp778-pl4805-rs11437&returnUrl=%5B%22%2Fcourses%2FMaths-for-Programming-174%3Ftab%3Dchapters%22%5D)
