<VIDEO_WIDGET>

<VIDEO_ID>3447</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# The Art of Pattern Printing: Level 3 - Regions and Inequalities

In Level 2, we learned how to draw perfectly straight diagonal lines using equations like `i == j` or `i + j == C`.

But what if we don't just want the outline? What if we want to fill an entire _region_ of the canvas?

In mathematics, a line splits a 2D plane into two halves. To color in one of those halves, we simply change our equation (`==`) into an inequality (`>=` or `<=`). Let's see how we can intersect multiple shaded regions to create solid shapes!

---

## Pattern 1: The Right-Aligned Solid Triangle

Before we intersect multiple regions, let's start by shading just one single region.

**The Problem:** Print a right-aligned solid triangle of height $N$.

For $N = 5$:

```text
    *
   **
  ***
 ****
*****
```

### 1. Defining the Canvas

The triangle has $N$ rows and $N$ columns. Our canvas is a standard $N \times N$ grid.

### 2. Shading the Region (Single Inequality)

Think back to Level 2. The diagonal line running from top-right to bottom-left is the secondary diagonal. Its equation is `i + j == n - 1`.

Notice that our solid triangle is essentially that diagonal line **plus everything to the right of it**.
If you pick any star to the right of the diagonal—for example, the bottom-right star at row 4, column 4 `(4, 4)`—you will see that the sum of coordinates is always strictly greater than $N - 1$ ($4 + 4 = 8 > 4$).

So, to print the diagonal AND everything to the right of it, we change the `==` to an inequality: `i + j >= n - 1`.

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        if (i + j >= n - 1) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 2: The Filled Pyramid (Solid Triangle)

**The Problem:** Print a solid, filled pyramid of height $N$.

For $N = 5$:

```text
    *
   ***
  *****
 *******
*********
```

### 1. Defining the Canvas

Just like the hollow triangle in Level 2, the bottom row has 5 stars on the left and 4 on the right. The canvas dimensions are **$N$ rows** by **$2N - 1$ columns**.

### 2. Shading the Region (Inequalities)

In Level 2, we drew the outline using two lines:

1. **Left Diagonal:** `i + j == n - 1`
2. **Right Diagonal:** `j == i + n - 1`

To print the _inside_ of the pyramid, we need to shade the region that is **greater than** the left line, AND **less than** the right line! We combine them using a logical `&&` (AND):

- Region to the right of the left diagonal: `i + j >= n - 1`
- Region to the left of the right diagonal: `j <= i + n - 1` (or `i + n - 1 >= j`)

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 2 * n - 1; j++) {
        // If the coordinate is inside BOTH shaded regions
        if (i + j >= n - 1 && j <= i + n - 1) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 3: The Filled Diamond

**The Problem:** Print a solid, filled diamond.

For $N = 5$:

```text
    *
   ***
  *****
 *******
*********
 *******
  *****
   ***
    *
```

### 1. Defining the Canvas

Our canvas is a massive **$(2N - 1) \times (2N - 1)$** square, just like the hollow diamond from Level 2.

### 2. Shading the Intersection of 4 Lines

A filled diamond is simply the intersection of the shaded regions bounded by all four diagonal lines! We change all 4 line equations into inequalities, pointing "inward" toward the center of the diamond:

1. **Top Left Boundary:** `i + j >= n - 1` (Shade bottom-right)
2. **Top Right Boundary:** `j <= i + n - 1` (Shade bottom-left)
3. **Bottom Left Boundary:** `i <= j + n - 1` (Shade top-right)
4. **Bottom Right Boundary:** `i + j <= 3 * n - 3` (Shade top-left)

If a coordinate `(i, j)` satisfies **ALL FOUR** inequalities simultaneously, it is inside the diamond!

```cpp
for (int i = 0; i < 2 * n - 1; i++) {
    for (int j = 0; j < 2 * n - 1; j++) {
        // Intersection of all 4 half-planes!
        if (i + j >= n - 1 && j <= i + n - 1 && i <= j + n - 1 && i + j <= 3 * n - 3) {
            cout << "*";
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

---

## Pattern 4: The Alphabetical Filled Diamond

**The Problem:** Print the exact same filled diamond, but use alphabetical characters based on the row number.

For $N = 5$:

```text
    a
   bbb
  ccccc
 ddddddd
eeeeeeeee
 fffffff
  ggggg
   hhh
    i
```

### The Positional Logic

By now, you are a master of the Canvas Paradigm. You know that the geometric boundaries have absolutely nothing to do with _what_ is printed.
The bounds (`>=` and `<=`) remain perfectly unchanged. Inside the `if` block, we just inject our Positional Logic: `char('a' + i)`.

```cpp
for (int i = 0; i < 2 * n - 1; i++) {
    for (int j = 0; j < 2 * n - 1; j++) {
        if (i + j >= n - 1 && j <= i + n - 1 && i <= j + n - 1 && i + j <= 3 * n - 3) {
            cout << char('a' + i);
        } else {
            cout << " ";
        }
    }
    cout << "\n";
}
```

## The Verdict

You have officially mastered the Canvas Technique. By starting with $1D$ lines (`==`) in Level 2, and transforming them into $2D$ half-planes (`>=`, `<=`) separated by `&&` operators in Level 3, you can now construct and fill absolutely any geometric shape without ever touching an inner-loop boundary variable!

In Level 4, we will learn how to take these isolated shapes and magically tile them infinitely across the screen using Modulo Arithmetic!

</READING_WIDGET>
