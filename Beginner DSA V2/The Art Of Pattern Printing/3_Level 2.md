<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# The Art of Pattern Printing: Level 2 - Diagonals and Lines

In Level 1, we learned how to draw outer boundaries by checking the extreme coordinates (like `i == 0` or `j == M-1`). But what if we need to draw lines *across* our canvas? 

Instead of jumping into messy loop logic, we will treat the canvas as a mathematical graph. Let's learn how to draw internal lines and diagonals!

---

## Pattern 1: The Plus Sign (`+`)

**The Problem:** Print a `+` shape of length $N$ and width $M$. Assume $N$ and $M$ are odd so there is a perfect center.

For $N = 5, M = 7$:
```text
   *   
   *   
*******
   *   
   *   
```

### The Logic
We are drawing two intersecting lines: a **Vertical Line** and a **Horizontal Line**.
- The horizontal line occurs perfectly in the middle row: `i == n / 2`.
- The vertical line occurs perfectly in the middle column: `j == m / 2`.

To draw the full `+`, we combine these two line equations with a logical OR (`||`).

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        if (i == n / 2 || j == m / 2) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 2: The "X" Cross (Diagonals)

**The Problem:** Print an `X` shape of size $N \times N$.

For $N = 5$:
```text
*   *
 * * 
  *  
 * * 
*   *
```

### The Logic
This shape is made of two crossing diagonal lines:
1. **The Primary Diagonal:** Goes from top-left to bottom-right. The row index always perfectly matches the column index! Equation: `i == j`.
2. **The Secondary Diagonal:** Goes from top-right to bottom-left. As the row index increases, the column index decreases. Their sum is always constant! Equation: `i + j == n - 1`.

Combine them together with a logical OR:

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        if (i == j || i + j == n - 1) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 3: The Inverted 'V' (Hollow Triangle)

**The Problem:** Print an inverted 'V' shape of height $N$.

For $N = 5$:
```text
    *    
   * *   
  *   *  
 *     * 
*       *
```

### 1. Defining the Canvas
This is no longer an $N \times N$ canvas! Look at the bottom row. There are 5 stars on the left, and 4 more on the right. 
The canvas dimensions are actually **$N$ rows** by **$2N - 1$ columns**. 

### 2. The Line Equations
We have two shifted diagonal lines meeting at the top center.
- **Left Diagonal:** This is a secondary diagonal shifted to the right. Equation: `i + j == n - 1`.
- **Right Diagonal:** This is a primary diagonal shifted to the right. Equation: `j == i + n - 1` (or `j - i == n - 1`).

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 2 * n - 1; j++) {
        if (i + j == n - 1 || j == i + n - 1) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 4: The Hollow Diamond

**The Problem:** Combine what we just learned to draw a fully enclosed hollow diamond!

For $N = 5$:
```text
    *    
   * *   
  *   *  
 *     * 
*       *
 *     * 
  *   *  
   * *   
    *    
```

### The Logic
Our canvas is now a massive **$(2N - 1) \times (2N - 1)$** square!
A diamond is just four shifted diagonal lines enclosing a space. Let's find all four line equations:
1. **Top Left:** `i + j == n - 1`
2. **Top Right:** `j - i == n - 1` $\rightarrow$ `j == i + n - 1`
3. **Bottom Left:** `i - j == n - 1` $\rightarrow$ `i == j + n - 1`
4. **Bottom Right:** This is a secondary diagonal shifted far down. The sum of the max coordinates is $(2N - 2) + (2N - 2)$, but we want the diagonal passing through $(N - 1, 2N - 2)$. Thus, the equation is: `i + j == 3 * n - 3`.

```cpp
for (int i = 0; i < 2 * n - 1; i++) {
    for (int j = 0; j < 2 * n - 1; j++) {
        if (i + j == n - 1 || j == i + n - 1 || i == j + n - 1 || i + j == 3 * n - 3) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 5: The Alphabet Diamond

**The Problem:** Print the exact same hollow diamond, but instead of stars, print the alphabetical character corresponding to the row!

For $N = 5$:
```text
    a    
   b b   
  c   c  
 d     d 
e       e
 f     f 
  g   g  
   h h   
    i    
```

### The Canvas + Positional Logic

We don't need to change our boundary logic at all! The canvas and the shape boundaries are perfectly identical to Pattern 4. 
We simply inject our **Positional Logic** from Level 1. If the boundary condition is met, we print `(char)('a' + i)` instead of `*`!

```cpp
for (int i = 0; i < 2 * n - 1; i++) {
    for (int j = 0; j < 2 * n - 1; j++) {
        if (i + j == n - 1 || j == i + n - 1 || i == j + n - 1 || i + j == 3 * n - 3) {
            cout << (char)('a' + i);
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Generalizing Lines on the Canvas

With the logic we've just learned, we can draw any straight line across our canvas simply by finding its constant $c$!

*   **Vertical Line:** $j == c$ (The column index never changes)
*   **Horizontal Line:** $i == c$ (The row index never changes)
*   **Primary Diagonal Shifted:** $i == j + c$ or $j == i + c$ (A diagonal shifted up or down). For example, `i == j + 1` shifts the primary diagonal exactly one unit down the Y-axis.
*   **Secondary Diagonal Shifted:** $i + j == c$ (A diagonal shifted left or right).

---

## The Verdict

By generalizing straight lines as simple algebraic equations like `i == j` or `i + j == C`, you can perfectly construct complex geometric boundaries like hollow diamonds without writing a single nested `while` loop! 

In Level 3, we will cross the final frontier: filling these shapes in using **Inequalities**!

</READING_WIDGET>
