---
title: "The Art of Pattern Printing: Level 1 - Simple Canvas Based Printing"
slug: "pattern-printing-level-1"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
videoStatus: "Not Published"
updatedAt: "2026-05-26"
description: "Master 2D pattern printing with the Canvas Approach. Learn to use coordinate geometry and simple boundaries."
---

# The Art of Pattern Printing: Level 1 - Simple Canvas

*Stop memorizing fragile nested loops. Learn the mathematical paradigm shift that turns complex pattern printing into an elegant game of coordinate geometry.*

## Why the Traditional Way is Broken

Let's talk about the elephant in the room: top-tier tech companies rarely ask direct pattern printing questions. Because of this, many students skip them. But this is a massive mistake. Pattern printing is actually a disguised training ground for 2D Matrix Traversal and Coordinate Geometry. 

The traditional approach of manually managing the changing boundaries of inner loops is highly prone to off-by-one errors and is incredibly hard to debug. In real-world software engineering—such as building a graphics rendering engine, writing GPU shaders, or rendering UI elements—we don't loop through "empty spaces" and then "filled spaces". 

Instead, we define a **Canvas**, iterate over every pixel `(i, j)`, and ask a **print function**: *"Based on your coordinates, what should you print?"*

Welcome to **The Canvas Approach**. 

### The Paradigm Shift
Instead of writing complex nested loops with shifting bounds, we will:
1. **Define the Canvas:** Determine the exact grid dimensions (e.g., $N \times M$). Write two simple, fixed loops to iterate through every coordinate $(i, j)$ on this canvas. In our canvas, think of `i` (rows) as the Y-axis pointing downwards, and `j` (columns) as the X-axis pointing right.
2. **The Print Function:** For every coordinate, call a separate logic function (e.g., `print_pixel(i, j)`) that directly outputs the correct character at that exact pixel based on mathematical rules.

Let's dive into Level 1: Simple Canvas Based Printing.

---

## Pattern 1: The Solid Rectangle

**The Problem:** Print a solid rectangle of length $N$ and width $M$ using `*`.

For $N = 3, M = 3$:
```text
***
***
***
```

### 1. Defining the Canvas
The dimensions are explicitly given: $N$ rows and $M$ columns. 
Our fixed outer loops will simply be:
```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        print_pixel();
    }
    cout << "\n";
}
```

### 2. The Print Function
For a solid rectangle, every single pixel on the canvas is a star. There are no spaces or empty regions. 
So our print function is incredibly simple. Regardless of the coordinate `(i, j)`, we print `*`.

```cpp
void print_pixel() {
    cout << "*";
}
```

This might seem trivial, but it sets up our mental model perfectly: **Decouple the grid traversal from the printing logic.**

---

## Pattern 2: The Hollow Rectangle (Outer Boundaries)

**The Problem:** Print a hollow rectangle of length $N$ and width $M$ using `*`. The borders are filled with `*` and the interior is empty.

For $N = 4, M = 5$:
```text
*****
*   *
*   *
*****
```

### 1. Defining the Canvas
Just like the solid rectangle, our canvas is $N \times M$. The loops remain exactly the same!

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        print_pixel(i, j, n, m);
    }
    cout << "\n";
}
```

### 2. The Print Function
Now, how do we mathematically define a "border"?
On an $(i, j)$ coordinate system (where $i$ goes from $0$ to $N-1$ and $j$ from $0$ to $M-1$), the borders are simply the extreme minimum and maximum coordinates.
- **Top Border:** $i = 0$
- **Bottom Border:** $i = N - 1$
- **Left Border:** $j = 0$
- **Right Border:** $j = M - 1$

If we are on any of these extreme coordinates, we print a `*`. Otherwise, we are inside the hollow region, so we print a space.

```cpp
void print_pixel(int i, int j, int n, int m) {
    if (i == 0 || i == n - 1 || j == 0 || j == m - 1) {
        cout << "*";
    } else {
        cout << " ";
    }
}
```

![A 2D grid diagram of size N rows and M columns. The vertical axis should be labeled 'i' (pointing down, indices 0 to N-1) and the horizontal axis labeled 'j' (pointing right, indices 0 to M-1). Highlight the top row (i=0), bottom row (i=N-1), left column (j=0), and right column (j=M-1) in a vibrant color. The interior cells should be left blank. Add small labels pointing to these four border lines with their respective equations to show how the logical "OR" operation forms a continuous border.](../Images/hollow-rectangle-logic-flowchart-01.png)

---

## Edge Cases & "Gotchas"

1. **🚨 CRITICAL: Zero-Indexing vs One-Indexing 🚨** 
   We mapped our canvas from $0$ to $Total-1$. If you accidentally start your loops at $1$, equations like `i == 0` will break completely. **Stick religiously to 0-indexed canvases.** The math is infinitely easier when the origin is $(0,0)$.

2. **Time Complexity:** The canvas approach guarantees we visit every coordinate exactly once. The time complexity is exactly $O(\text{rows} \times \text{cols})$. 

3. **Space Complexity:** Because we evaluate coordinates dynamically on the fly and print directly to the output stream, the **Auxiliary Space Complexity is strictly $O(1)$**. We *simulate* a 2D array without ever allocating one in memory!

## The Verdict

By switching from **Loop Boundary Management** to **Coordinate Geometry**, you decouple the traversal of the grid from the logic of what to print. In Level 1, we learned how to isolate the outer boundaries. In the next level, we will learn how to draw diagonal lines across our canvas!

---

## Let's Practice!

Pattern printing is best learned by doing. Test your newfound coordinate geometry skills with these problems!

- **[Hollow Pattern](https://maang.in/problems/Hollow-Pattern-1089)**

---

## Video Explanation

[![Pattern Printing: The Canvas Approach](../Images/video-lecture-thumbnail.jpg)]()