<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# The Art of Pattern Printing: Level 1 - Simple Canvas

*Stop memorizing fragile nested loops. Learn the mathematical paradigm shift that turns complex pattern printing into an elegant game of coordinate geometry.*

## Why the Traditional Way is Broken

Let's talk about the elephant in the room: top-tier tech companies rarely ask direct pattern printing questions. Because of this, many students skip them. But this is a massive mistake. Pattern printing is actually a disguised training ground for 2D Matrix Traversal and Coordinate Geometry. 

The traditional approach of manually managing the changing boundaries of inner loops is highly prone to off-by-one errors and is incredibly hard to debug. In real-world software engineering—such as building a graphics rendering engine, writing GPU shaders, or rendering UI elements—we don't loop through "empty spaces" and then "filled spaces". 

Instead, we define a **Canvas**, iterate over every pixel `(i, j)`, and ask a **print function**: *"Based on your coordinates, what should you print?"*

Welcome to **The Canvas Approach**. 

### The Paradigm Shift
Instead of writing complex nested loops with shifting bounds, we will:

1. **Define the Canvas:** Determine the exact grid dimensions (e.g., $N \times M$). Write two simple, fixed loops to iterate through every coordinate $(i, j)$ on this canvas. In our canvas, think of `i` (rows) as the Y-axis pointing downwards, and `j` (columns) as the X-axis pointing right. Notice how indexing rows `0` to `N-1` and columns `0` to `M-1` works identically to 2D Arrays and Matrices in memory!

2. **Positional Logic:** For every coordinate $(i, j)$, we will decide what to print based on its position.

Let's dive into Level 1: Simple Canvas Based Printing.

---

## Pattern 1: The Solid Rectangle

**The Problem:** Print a solid rectangle of length $N$ and width $M$ using `*`.

For $N = 5, M = 6$:
```text
******
******
******
******
******
```

### 1. Defining the Canvas
The dimensions are explicitly given: $N$ rows and $M$ columns. 
Our fixed outer loops will simply be:
```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        // We will put our print logic here
    }
    cout << "\n";
}
```

### 2. The Print Function
For a solid rectangle, every single pixel on the canvas is a star. There are no spaces or empty regions. 
So our print logic is incredibly simple. Regardless of the coordinate `(i, j)`, we print `*`.

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        cout << "*";
    }
    cout << "\n";
}
```

This might seem trivial, but it sets up our mental model perfectly: **Decouple the grid traversal from the printing logic.**

---

## Pattern 2: Dynamic Positional Logic

**The Problem:** Print a rectangle of length `N` and width `M` where each row is filled with the row's corresponding line number (1-indexed).
For `N = 5, M = 6`:
```text
111111
222222
333333
444444
555555
```

### 1. Defining the Canvas

Once again, the canvas is exactly the same. We iterate through `i` from `0` to `N - 1` and `j` from `0` to `M - 1`.

### 2. The Print Function (Positional Logic)

Instead of printing a static `*`, we need to ask: *"What goes here based on my coordinates?"*
Looking at the pattern, the value printed depends entirely on the current row. If we are on row `i = 0`, we print `1`. If we are on row `i = 1`, we print `2`.
The mathematical relationship is simply `i + 1`. We don't even need an `if` statement; we just inject our positional logic directly into the print output:
```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        // Positional Logic: Print the row index + 1
        cout << i + 1;
    }
    cout << "\n";
}
```

---

## Pattern 3: The Hollow Rectangle (Outer Boundaries)

**The Problem:** Print a hollow rectangle of length $N$ and width $M$ using `*`. The borders are filled with `*` and the interior is empty.

For $N = 5, M = 6$:
```text
******
*    *
*    *
*    *
******
```

### 1. Defining the Canvas
Just like the solid rectangle, our canvas is $N \times M$. The loops remain exactly the same!

### 2. The Print Function
Now, how do we mathematically define a "border"?
On an $(i, j)$ coordinate system (where $i$ goes from $0$ to $N-1$ and $j$ from $0$ to $M-1$), the borders are simply the extreme minimum and maximum coordinates.
- **Top Border:** $i = 0$
- **Bottom Border:** $i = N - 1$
- **Left Border:** $j = 0$
- **Right Border:** $j = M - 1$

If we are on any of these extreme coordinates, we print a `*`. Otherwise, we are inside the hollow region, so we print a space.

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        // Positional Logic for Boundaries
        if (i == 0 || i == n - 1 || j == 0 || j == m - 1) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/b74822cc-a444-4d7f-9098-7c0325567dfa.png" alt="Hollow-Rectangle-Logic-Flowchart-01" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## Edge Cases & "Gotchas"

1. **🚨 CRITICAL: Zero-Indexing vs One-Indexing 🚨** 
   We mapped our canvas from $0$ to $Total-1$. If you accidentally start your loops at $1$, equations like `i == 0` will break completely. **Stick religiously to 0-indexed canvases.** The math is infinitely easier when the origin is $(0,0)$.

2. **Time Complexity:** The canvas approach guarantees we visit every coordinate exactly once. The time complexity is exactly $O(\text{rows} \times \text{cols})$. 

3. **Space Complexity:** Because we evaluate coordinates dynamically on the fly and print directly to the output stream, the **Auxiliary Space Complexity is strictly $O(1)$**. We *simulate* a 2D array without ever allocating one in memory!

## The Verdict

By switching from **Loop Boundary Management** to **Coordinate Geometry**, you decouple the traversal of the grid from the logic of what to print. In Level 1, we learned how to isolate the outer boundaries. In the next level, we will learn how to draw diagonal lines across our canvas!

</READING_WIDGET>
