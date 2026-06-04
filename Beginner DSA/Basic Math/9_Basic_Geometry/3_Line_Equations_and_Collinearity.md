---
title: "Line Equations & Collinearity"
slug: "line-equations-collinearity"
track: "beginner-dsa"
level: "Beginner"
order: 3
status: "Draft"
duration: ""
videoStatus: "Not Published"
updatedAt: "2026-06-04"
description: "Why you should never use slopes in CP! Learn the robust 2D cross product for checking collinearity and orientation."
---

# Line Equations & Collinearity

In high school math, we were taught to rely on equations with division (like slope-intercept) to analyze lines. In competitive programming, division is your worst enemy because it introduces floating-point precision issues and the fatal "division by zero" runtime error.

Let's re-learn how to handle lines using robust integer math.

---

## 1. The Slope Trap

In geometry, the **slope** (often represented by $m$) tells you how steep a line is. It is mathematically defined as the "rise over run"—how much the line goes up vertically ($y_2 - y_1$) divided by how much it goes across horizontally ($x_2 - x_1$). 
$$m = \frac{y_2 - y_1}{x_2 - x_1}$$

In high school math, you likely learned the slope-intercept form of a line using this slope: $y = mx + c$. 
In competitive programming, **this formula is a trap**. 

If the two points form a perfectly vertical line, the horizontal distance is zero ($x_2 - x_1 = 0$). Your code will attempt to divide by zero and crash with a **Runtime Error**! Furthermore, dividing numbers in C++ creates floating-point precision issues (`double`), which causes logically correct algorithms to fail tight test cases.

**The CP Fix:** Never divide! If you want to check if three points $(A, B, C)$ are collinear (meaning they lie on the exact same straight line), you don't calculate and compare their slopes like this:
$$\frac{y_2 - y_1}{x_2 - x_1} = \frac{y_3 - y_2}{x_3 - x_2}$$

Instead, you cross-multiply the denominators to create a bulletproof, division-free integer equation:
$$(y_2 - y_1) \times (x_3 - x_2) == (y_3 - y_2) \times (x_2 - x_1)$$
If this equation is true, the points are collinear. Zero division, zero precision errors!

---

## 2. 2D Cross Product (Orientation)

What if you don't just want to know if points are collinear, but you want to know their *orientation*? If you are standing at Point A and walking toward Point B, do you have to turn **left** or **right** to get to Point C?

This is elegantly solved using the **2D Cross Product**. By treating the line segments as vectors (directional arrows), we can mathematically calculate their determinant. 

For three points $A(x_1, y_1)$, $B(x_2, y_2)$, and $C(x_3, y_3)$, the formula is:
$$\text{Cross Product} = (x_2 - x_1) \times (y_3 - y_1) - (y_2 - y_1) \times (x_3 - x_1)$$

- **If Cross Product > 0:** Point C is to the **Left** (Counter-Clockwise turn).
- **If Cross Product < 0:** Point C is to the **Right** (Clockwise turn).
- **If Cross Product == 0:** The points are perfectly **Collinear**.

![A diagram showing three scenarios of points P1, P2, and P3. In the first, the path from P1 to P2 to P3 curves left (Counter-Clockwise, Cross Product > 0). In the second, it curves right (Clockwise, Cross Product < 0). In the third, all three points lie perfectly on a single straight line (Collinear, Cross Product = 0).](../Images/cross_product_turns.png)

> 🚨 **Use 64-bit Integers!** 
> The cross product multiplies coordinate differences. If coordinates can go up to $10^9$, squaring them will result in $10^{18}$, heavily overflowing a standard 32-bit `int`. **Always** use `long long` for cross product components to guarantee $100\%$ precision!

---

## Let's Practice!

Master the cross-product technique with these collinearity problems:

- **[Check If It Is a Straight Line](https://leetcode.com/problems/check-if-it-is-a-straight-line/description/)**
- **[Valid Boomerang](https://leetcode.com/problems/valid-boomerang/description/)**

---

## Video Explanation

[![Line Equations and Collinearity](../Images/video-lecture-thumbnail.jpg)]()
