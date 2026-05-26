---
title: "The Art of Pattern Printing: Level 2 - Diagonals and Lines"
slug: "pattern-printing-level-2"
track: "beginner-dsa"
level: "Beginner"
order: 2
status: "Draft"
duration: ""
videoStatus: "Not Published"
updatedAt: "2026-05-26"
description: "Master drawing primary and secondary diagonals using coordinate geometry equations."
---

# The Art of Pattern Printing: Level 2 - Diagonals and Lines

In Level 1, we learned how to draw outer boundaries by checking the extreme coordinates (like `i == 0` or `j == N-1`). But what if we need to draw lines *across* our canvas? 

Instead of jumping into messy loop logic, we can look at the canvas like a mathematical graph. Let's learn how to draw diagonals!

---

## Pattern 1: The Primary Diagonal

**The Problem:** Print a diagonal line of stars from the top-left to the bottom-right.

For $N = 5$:
```text
*    
 *   
  *  
   * 
    *
```

### 1. Defining the Canvas
Just like before, we have an $N \times N$ canvas. Our standard loops remain completely unchanged.
```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        print_pixel(i, j, n);
    }
    cout << "\n";
}
```

### 2. The Print Function (Coordinate Geometry)
Let's look at the coordinates of the stars:
- Row 0: `(0, 0)`
- Row 1: `(1, 1)`
- Row 2: `(2, 2)`
- Row 3: `(3, 3)`
- Row 4: `(4, 4)`

The pattern is blatantly obvious! The row index $i$ is always exactly equal to the column index $j$. This is the mathematical equation for a line passing through the origin at a 45-degree angle.

```cpp
void print_pixel(int i, int j, int n) {
    if (i == j) {
        cout << "*";
    } else {
        cout << " ";
    }
}
```

---

## Pattern 2: The Secondary Diagonal

**The Problem:** Print a diagonal line of stars from the top-right to the bottom-left.

For $N = 5$:
```text
    *
   * 
  *  
 *   
*    
```

### 1. Defining the Canvas
We still have an $N \times N$ canvas. 

### 2. The Print Function (Negative Slope)
Let's analyze the coordinates of these stars:
- Row 0: `(0, 4)`
- Row 1: `(1, 3)`
- Row 2: `(2, 2)`
- Row 3: `(3, 1)`
- Row 4: `(4, 0)`

Notice how the row index increases while the column index decreases? This means the sum of the coordinates is constant!
$0 + 4 = 4$
$1 + 3 = 4$
$2 + 2 = 4$

Since $N = 5$, the constant sum is exactly $N - 1$. 
The mathematical equation for this diagonal is: $i + j == N - 1$.

```cpp
void print_pixel(int i, int j, int n) {
    if (i + j == n - 1) {
        cout << "*";
    } else {
        cout << " ";
    }
}
```

![A square 2D grid diagram of size N by N. Label the vertical axis 'i' (pointing down) and horizontal axis 'j' (pointing right). Draw a vibrant blue diagonal line from the top-left to bottom-right, labeling it 'Primary Diagonal: i == j'. Draw a vibrant red diagonal line from the top-right to bottom-left, labeling it 'Secondary Diagonal: i + j == N - 1'. Show the intersection point in the center.](../Images/diagonals.png)

---

## Generalizing Lines on the Canvas

With this logic, we can draw any straight line across our canvas simply by finding its constant $c$!

*   **Vertical Line:** $j == c$ (The column index never changes)
*   **Horizontal Line:** $i == c$ (The row index never changes)
*   **Primary Diagonal Shifted:** $i == j + c$ or $j == i + c$ (A diagonal shifted up or down). For example, `i == j + 1` shifts the primary diagonal exactly one unit down the Y-axis.
*   **Secondary Diagonal Shifted:** $i + j == c$ (A diagonal shifted left or right).

This mathematical generalization is the core secret behind drawing complex shapes like diamonds and butterflies.

---

## Edge Cases & "Gotchas"

1. **Intersection Points:** What if you want to draw an "X" shape (both diagonals)? You don't need two sets of loops! You simply combine the mathematical conditions using a logical OR: `if (i == j || i + j == n - 1)`. 
2. **Matrix Diagonals:** The equations $i == j$ and $i + j == N - 1$ aren't just for printing shapes. They are the exact same conditions you will use in technical interviews when asked to "Find the sum of the diagonals of a 2D Matrix". 

## The Verdict

By treating the canvas as a coordinate system, we turned complex spatial reasoning into simple algebra. In the next level, we will learn how to turn these 1D lines into 2D regions using **inequalities**!

---

## Video Explanation

[![Pattern Printing: Diagonals and Lines](../Images/video-lecture-thumbnail.jpg)]()
