---
title: "The Art of Pattern Printing: Level 5 - Pattern Repetition (Modulo Magic)"
slug: "pattern-printing-level-5"
track: "beginner-dsa"
level: "Beginner"
order: 5
status: "Draft"
duration: ""
videoStatus: "Not Published"
updatedAt: "2026-05-26"
description: "Master the ultimate cheat code for drawing infinite repeating patterns and grids using the Modulo operator."
---

# The Art of Pattern Printing: Level 5 - Pattern Repetition (Modulo Magic)

Welcome to the final boss of pattern printing.

You now know how to draw lines, shade regions, and intersect them to form complex shapes. But what if an interview asks you to take that shape and tile it 100 times across the screen like wallpaper?

If you try to use nested loops for every single tile, your code will explode in complexity. Instead, we use the most powerful mathematical tool for periodic boundaries: **The Modulo Operator (`%`)**.

---

## Pattern 1: Horizontal Repetition

**The Problem:** Print a primary diagonal `\` that repeats itself horizontally 4 times. 

For $N = 5$:
```text
*    *    *    *    
 *    *    *    *   
  *    *    *    *  
   *    *    *    * 
    *    *    *    *
```

### 1. Defining the Canvas
A single diagonal takes an $N \times N$ canvas. Since we want to repeat it 4 times horizontally, our total columns will be $4 \times N$.
```cpp
int total_cols = 4 * n;
for (int i = 0; i < n; i++) {
    for (int j = 0; j < total_cols; j++) {
        print_pixel(i, j, n);
    }
    cout << "\n";
}
```

### 2. The Print Function (The Modulo Trick)
Think about a single diagonal. From Level 2, we know the equation is `i == j`.
But here, we want `j` to "reset" back to 0 every time it hits $N$. 

If $N = 5$:
When $j = 5$, we want to treat it like $j = 0$.
When $j = 6$, we want to treat it like $j = 1$.

This is exactly what the modulo operator does! By taking the remainder `j % n`, we force the column coordinate to infinitely loop from $0$ to $N-1$. 

```cpp
void print_pixel(int i, int j, int n) {
    if (i == (j % n)) {
        cout << "*";
    } else {
        cout << " "; 
    }
}
```
That's it! One extra `%` sign, and you can repeat a pattern infinitely across the X-axis.

---

## Pattern 2: Simple Grids (The Stride)

Before we jump into overlapping diagonals, let's look at a simpler, very common interview pattern: a block grid.

**The Problem:** Print a grid-like pattern of blocks. Every block is bounded by `*` and filled with `.`.
For $N = 3$ (blocks vertically), $M = 4$ (blocks horizontally). Each block is $3 \times 3$ pixels.
```text
*************
*..*..*..*..*
*..*..*..*..*
*************
*..*..*..*..*
*..*..*..*..*
*************
*..*..*..*..*
*..*..*..*..*
*************
```

### 1. Defining the Canvas
Instead of writing nested loops per block, let's step back and look at the entire canvas.
Each of the $N$ blocks takes 3 vertical pixels (1 top border, 2 dots). Then there is 1 final bottom border for the entire grid. So, $\text{total rows} = 3N + 1$.
Similarly, $\text{total columns} = 3M + 1$.

To avoid "magic numbers" (a red flag in interviews), we introduce a `stride` variable to represent the block size.

```cpp
int stride = 3;
int total_rows = stride * n + 1;
int total_cols = stride * m + 1;

for (int i = 0; i < total_rows; i++) {
    for (int j = 0; j < total_cols; j++) {
        print_pixel(i, j, stride);
    }
    cout << "\n";
}
```

### 2. The Print Function (Grid Modulo)
When exactly do the `*` borders appear?
Look at the row indices for the horizontal lines: $i = 0$, $i = 3$, $i = 6$, $i = 9$...
Look at the column indices for the vertical lines: $j = 0$, $j = 3$, $j = 6$, $j = 9$, $j = 12$...

They appear exactly when the index is a multiple of the stride!
Mathematically: `i % stride == 0` OR `j % stride == 0`.

```cpp
void print_pixel(int i, int j, int stride) {
    if (i % stride == 0 || j % stride == 0) {
        cout << "*";
    } else {
        cout << ".";
    }
}
```

---

## Pattern 3: Overlapping 2D Grid Repetition

What if we want to repeat a pattern on **both** the X-axis and the Y-axis? We simply apply modulo to both $i$ and $j$!

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

### 2. The Print Function (2D Modulo)
Let's define the modulo period: `P = n - 1`.
Whenever we evaluate our coordinates, we wrap both $i$ and $j$ into this period:
`int mod_i = i % P;`
`int mod_j = j % P;`

Now, we just ask: inside this small $P \times P$ local box, what are the equations for an "X"?
We already know them from Level 4!
- Primary Diagonal: `mod_i == mod_j`
- Secondary Diagonal: `mod_i + mod_j == P`

```cpp
void print_pixel(int i, int j, int n) {
    int P = n - 1; // The repeating period
    int mod_i = i % P;
    int mod_j = j % P;
    
    if (mod_i == mod_j || mod_i + mod_j == P) {
        cout << "*";
    } else {
        cout << " "; 
    }
}
```

![A large 2D grid filled with repeating 'X' shapes. Use vertical and horizontal grid lines to visually slice the canvas into blocks of size P by P (where P = N-1). In one of the blocks, highlight the local (mod_i, mod_j) coordinates. This visualizes how the global canvas is just the exact same local PxP block tiled infinitely.](../Images/repeating_x_pattern.png)

---

## Edge Cases & "Gotchas"

1. **🚨 CRITICAL: Zero-Indexing is MANDATORY 🚨** 
   If you didn't listen to the warnings in Levels 1 through 4, you will completely crash and burn here. The modulo operator `%` maps perfectly to `0`-indexed arrays. `5 % 5 == 0`, which beautifully wraps back to the start. If you try to use `1`-indexed loops, your modulo math will shift, skip columns, and completely destroy the pattern. **Always start your loops at 0.**

2. **Identifying the True Period:**
   The hardest part of Level 5 is calculating the repeating period `P`. If shapes are side-by-side with no overlap, the period is $N$. If they share a border or corner (like our X grid), the period is $N - 1$. Always sketch the first two tiles to count the exact pixel distance between the start of Tile 1 and the start of Tile 2.

3. **The Negative Modulo Trap (CP Pro-Tip):**
   C++ has a notoriously dangerous quirk: its `%` operator is a remainder operator, not a true mathematical modulo. It fails completely on negative numbers! For example, `-1 % 5` in C++ returns `-1`, not `4`. 
   If you try to shift your periodic grids left or up (e.g., `(i - 2) % stride`), you might get a negative index and the pattern will completely break.
   Always use the bulletproof competitive programming formula for a safe, positive modulo: `((i % P) + P) % P`.

## The Final Verdict

You did it. You completed the Canvas Approach.

What used to be an intimidating nightmare of 6-deep nested `for` loops, confusing boundary flags, and off-by-one errors has been completely dismantled. By treating the console as a geometric plane, you can now draw lines (`==`), shade regions (`>=`), compose shapes (`||`), and repeat them infinitely (`%`) with absolute ease. 

You aren't just printing patterns anymore; you are writing the foundation of graphics rendering.

---

## Let's Practice!

Test your final form with these grid problems. Use the modulo trick!

- **[Pattern Problem 1 AZ101](https://maang.in/problems/Pattern-Problem-1-AZ101-317)**
- **[Pattern Problem 2 AZ101](https://maang.in/problems/Pattern-Problem-2-AZ101-318)**
- **[Zig-zag Snake](https://maang.in/problems/Zigzag-Snake-772)**

---

## Video Explanation

[![Pattern Printing: The Canvas Approach](../Images/video-lecture-thumbnail.jpg)]()
