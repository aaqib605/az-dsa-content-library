<VIDEO_WIDGET>

<VIDEO_ID>3448</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# The Art of Pattern Printing: Level 4 - The Magic of Repetition

We have officially mastered the Canvas Technique. We can draw lines (`==`) and fill regions (`>=`). But there is one final pattern printing challenge that strikes fear into the hearts of beginners: **Infinite Repeating Patterns.**

How do you draw a continuous zig-zag wave that repeats 20 times across the screen? Traditional nested loops collapse entirely under this requirement.

Welcome to Level 4, where we introduce the **Monomer and Polymer** technique using the magic of Modulo Arithmetic (`%`)!

---

## The Core Concept: Monomers and Polymers

In chemistry, a complex _Polymer_ is created by chaining together simple, repeating blocks called _Monomers_. We apply the exact same logic to our 2D canvas.

If you have an equation that successfully draws a shape inside a $4 \times 4$ box, you don't need to write a new equation for the next box. You simply take the column index $j$ and apply **Modulo 4** (`j % 4`).

Because `j % 4` traps the coordinate mathematically between $0$ and $3$, the $4 \times 4$ logic will seamlessly repeat itself infinitely across the $X$-axis!

---

## Pattern 1: The Infinite Intersecting "X" Grid

**The Problem:** Print an infinite grid of intersecting "X" patterns. The "X" shapes should share their corner stars.

For $N = 5$, repeated 4 times in both directions:

```text
*   *   *   *   *
 * * * * * * * *
  *   *   *   *
 * * * * * * * *
*   *   *   *   *
 * * * * * * * *
  *   *   *   *
 * * * * * * * *
*   *   *   *   *
... (and so on)
```

### 1. Defining the Canvas

A single "X" fits in an $N \times N$ box. But wait! They share borders (the corner stars overlap). This means the actual "period" (the distance before the pattern starts repeating) is $N - 1$.

Total rows: $4 \times (N - 1) + 1$
Total columns: $4 \times (N - 1) + 1$

### 2. The Inline Logic (2D Modulo)

Let's define the modulo period: `P = n - 1`.
Whenever we evaluate our coordinates, we wrap both $i$ and $j$ into this period:
`int mod_i = i % P;`
`int mod_j = j % P;`

Now, we just ask: inside this small $P \times P$ local box, what are the equations for an "X"?
We already know them from Level 2!

- Primary Diagonal: `mod_i == mod_j`
- Secondary Diagonal: `mod_i + mod_j == P`

```cpp
int P = n - 1; // The repeating period
int rows = 4 * P + 1;
int cols = 4 * P + 1;

for (int i = 0; i < rows; i++) {
    for (int j = 0; j < cols; j++) {
        int mod_i = i % P;
        int mod_j = j % P;

        if (mod_i == mod_j || mod_i + mod_j == P) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 2: The Continuous Zig-Zag (The Ultimate Interview Pattern)

This is one of the most frequently asked pattern printing questions.

**The Problem:** Print a continuous Zig-Zag (a `W` or `M` wave) of height $N$.

For $N = 4$:

```text
*     *     *     *     *
 *   * *   * *   * *   *
  * *   * *   * *   * *
   *     *     *     *
```

### 1. Identify the Monomer

If you look closely at the zig-zag, the repeating unit is a "V" shape.
To build a "V" of height $N=4$, how many columns does it take before it starts repeating?

- It goes down for 4 steps, and back up for 2 steps (the top points are shared).
- Mathematically, the length of the repeating monomer block for _any_ zig-zag is always **$2N - 2$**.
- For $N = 4$, the monomer length is $2(4) - 2 = 6$.

### 2. Build the Monomer Line Equations

Inside a $4 \times 6$ block, a "V" is just two lines:

1. **The Downward Stroke:** A primary diagonal! `i == j`.
2. **The Upward Stroke:** A secondary diagonal. Since it needs to hit the bottom at row $3$ and go back up to row $0$ at column $6$, its equation is `i + j == 6`.
   _(Notice that 6 is exactly our monomer length $2N - 2$!)_

### 3. Create the Polymer

We wrap every instance of `j` with modulo **$2N - 2$**.

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 25; j++) { // Loop j to any width you want!
        int mod_val = 2 * n - 2;

        // Downward Stroke || Upward Stroke
        if (i == (j % mod_val) || i + (j % mod_val) == mod_val) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 3: The Alphabetical Zig-Zag

**The Problem:** Print the continuous Zig-Zag, but replace the stars with the alphabetical character of the corresponding row!

For $N = 5$:

```text
a       a       a       a
 b     b b     b b     b
  c   c   c   c   c   c
   d d     d d     d d
    e       e       e
```

By now, you should be smiling. The geometric boundaries are absolutely flawless. We just inject our Positional Logic!

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 25; j++) {
        int mod_val = 2 * n - 2;

        if (i == (j % mod_val) || i + (j % mod_val) == mod_val) {
            cout << char('a' + i);
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

## The Verdict

By combining coordinate geometry and the magical repetition of the Modulo (`%`) operator, we can draw and repeat highly complex intersecting shapes without adding a single extra `for` loop.

But what about patterns that radiate from a center point, like spiral squares or elegant diamonds? In the final level, Level 5, we will cross the ultimate frontier: using Absolute Values to calculate geometric distances!

</READING_WIDGET>
