<VIDEO_WIDGET>

<VIDEO_ID>3449</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# The Art of Pattern Printing: Level 5 - Absolute Value & Distances

Welcome to the final level.

You've learned how to draw lines (`==`), shade regions (`>=`), intersect them (`&&`), and repeat them infinitely (`%`).

But there is one final class of problems that are extremely famous in interviews: **Concentric Patterns**. These are shapes that radiate outward from a center point. If you try to build these using intersecting lines, the math gets incredibly tangled.

Instead, we will use a concept you learned in the Basic Geometry module: **Distances!**

---

## Pattern 1: Concentric Number Squares (Chebyshev)

**The Problem:** Print a grid of numbers where the maximum value $N$ is on the outer border, and the numbers decrease to $1$ at the center.

For $N = 4$:

```text
4444444
4333334
4322234
4321234
4322234
4333334
4444444
```

### 1. Defining the Canvas & Center

The grid has $2N - 1$ rows and $2N - 1$ columns.
The absolute center of this grid is exactly at coordinate `(n - 1, n - 1)`.

### 2. The Positional Logic (Chebyshev Distance)

Look at the numbers. The center is `1`. The ring around it is `2`. The ring around that is `3`.
The value printed is exactly the **Chebyshev Distance** (the "Chess King" distance) from the center!

In our Basic Geometry module, we learned the formula for Chebyshev Distance: `max(|x1 - x2|, |y1 - y2|)`.
If we calculate the distance from our current coordinate `(i, j)` to the `center`, and add $1$, we perfectly generate this pattern!

```cpp
int size = 2 * n - 1;
int center = n - 1;

for (int i = 0; i < size; i++) {
    for (int j = 0; j < size; j++) {
        int distance_x = abs(j - center);
        int distance_y = abs(i - center);

        int val = max(distance_x, distance_y) + 1;
        cout << val;
    }
    cout << "\n";
}
```

That's it! What would normally take a terrifying spiral matrix traversal is solved in 3 lines of absolute value math.

---

## Pattern 2: The Elegant Diamond (Manhattan)

In Level 4, we built a Hollow Diamond using the intersection of four shifted diagonal lines (`i + j == n - 1 || ...`). While it works perfectly, it's quite long to type out. Let's optimize it.

**The Problem:** Print a Hollow Diamond of size $N$.

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

### The Manhattan Formula

A diamond is mathematically defined as the set of all points that have the exact same **Manhattan Distance** from a center point!

The center of our $(2N - 1)$ canvas is `(n - 1, n - 1)`.
The Manhattan Distance formula is: `|x1 - x2| + |y1 - y2|`.

If we check if the Manhattan Distance from our current coordinate `(i, j)` to the `center` is exactly equal to the radius ($N - 1$), it will perfectly draw a hollow diamond!

```cpp
int size = 2 * n - 1;
int center = n - 1;
int radius = n - 1;

for (int i = 0; i < size; i++) {
    for (int j = 0; j < size; j++) {
        int distance_x = abs(j - center);
        int distance_y = abs(i - center);

        if (distance_x + distance_y == radius) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

If you want to fill the diamond solid, just change `==` to `<= radius`!

---

## The Ultimate Canvas Framework

Congratulations! You have officially conquered 2D Pattern Printing. You will never need to memorize a fragile nested `while` loop again.

Here is your universal 5-step framework to solve any pattern printing problem in a technical interview:

1. **The Canvas:** Determine the absolute grid size (e.g., $N \times M$ or $(2N-1) \times (2N-1)$) and write two standard 0-indexed `for` loops.
2. **The Monomer:** If the pattern repeats, isolate the smallest repeating block and find its length $P$. Wrap your coordinates in modulo: `i % P`.
3. **The Lines:** Find the geometric equations for the straight lines (`i == j`, `i + j == c`).
4. **The Regions:** If the pattern is filled or composite, convert lines into half-planes (`>=`, `<=`) and combine them using `&&` (intersection) or `||` (union).
5. **Positional Values:** Use the raw `i` and `j` coordinates to calculate dynamic characters (`char('A' + j)`) or absolute distances (`abs()`).

You aren't just printing patterns anymore—you are mathematically rendering graphics.

</READING_WIDGET>
