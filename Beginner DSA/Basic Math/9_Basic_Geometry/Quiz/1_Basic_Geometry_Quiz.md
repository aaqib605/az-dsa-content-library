---
title: "Basic Geometry Quiz"
slug: "basic-geometry-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your knowledge of grid distances, coordinate geometry, Pick's theorem, and integer-safe math in competitive programming."
---

# Basic Geometry Quiz

Choose the correct answer for each question.

## Questions

### 1. What is the safest way to compare the Euclidean distance between points in competitive programming?
A. Always use `sqrt()` and store the result in a `double`  
B. Use `sqrt()` but cast the result back to an `int`  
C. Avoid `sqrt()` entirely and compare the squared integer distances ($d^2$)  
D. Use the Manhattan distance formula instead as an approximation  

### 2. When calculating squared Euclidean distance, if the coordinates can reach up to $10^9$, what critical C++ trap must you avoid?
A. The numbers will exceed the `long long` limit, so you must use BigInt  
B. `sqrt()` will return a negative number  
C. $(10^9)^2 = 10^{18}$, which overflows a standard 32-bit `int`, so you must cast to a 64-bit `long long`  
D. Squared distances are always perfectly safe and never overflow  

### 3. If a character can move one step horizontally, vertically, OR diagonally, which distance metric perfectly describes the minimum steps required to reach a target?
A. Euclidean Distance  
B. Manhattan Distance  
C. Chebyshev Distance (Chess King Distance)  
D. Minkowski Distance  

### 4. What is the mathematically robust way to check if three points $A, B, C$ are collinear without using slope division?
A. $\frac{y_2 - y_1}{x_2 - x_1} == \frac{y_3 - y_2}{x_3 - x_2}$  
B. $(y_2 - y_1) \times (x_3 - x_2) == (y_3 - y_2) \times (x_2 - x_1)$  
C. $\max(|x_1-x_2|, |y_1-y_2|) == \max(|x_2-x_3|, |y_2-y_3|)$  
D. Check if their Euclidean distances sum up perfectly using `sqrt()`  

### 5. You are finding the overlap of two axis-aligned rectangles using the Min-Max Boundary Trick. Why is it absolutely necessary to clamp the width and height to $0$ using `max(0LL, right - left)`?
A. To ensure the area doesn't overflow a 32-bit integer  
B. Because multiplying a negative width by a negative height (when they don't overlap) mathematically creates a fake positive area  
C. To automatically cast the numbers to `long long`  
D. It is not necessary; negative dimensions are fine in CP  

### 6. Which equation correctly and safely checks if a point $(x, y)$ is strictly inside or on the boundary of a circle with center $(h, k)$ and radius $r$?
A. $\sqrt{(x-h)^2 + (y-k)^2} \le r$  
B. $|x - h| + |y - k| \le r$  
C. $(x - h)^2 + (y - k)^2 \le r$  
D. $(x - h)^2 + (y - k)^2 \le r^2$  

### 7. Why do CP templates for the Shoelace Formula typically calculate and compare $2 \times \text{Area}$ instead of just the Area itself?
A. Dividing by 2 introduces `.5` decimal values, requiring floats. Keeping it as $2 \times \text{Area}$ ensures the math remains in pure integers.  
B. Because the Shoelace formula inherently calculates exactly double the area and it's impossible to divide it.  
C. To prevent negative area values from occurring.  
D. $2 \times \text{Area}$ is a requirement for Pick's Theorem.  

### 8. According to the Area Sum Method, a point $P$ is inside a triangle $ABC$ if:
A. The Shoelace area of $PAB$ is zero  
B. The Cross Product of $PA$ and $PB$ is strictly positive  
C. $2\times\text{Area}(ABC) == 2\times\text{Area}(PAB) + 2\times\text{Area}(PBC) + 2\times\text{Area}(PCA)$  
D. The Manhattan distance from $P$ to the centroid is minimized  

### 9. Using Pick's Theorem ($\text{Area} = I + \frac{B}{2} - 1$), you need to find the number of integer boundary points $B$ on a line segment between $(x_1, y_1)$ and $(x_2, y_2)$. Which mathematical function provides the exact number of points?
A. $\min(|x_1 - x_2|, |y_1 - y_2|)$  
B. $\max(|x_1 - x_2|, |y_1 - y_2|)$  
C. $|x_1 - x_2| \times |y_1 - y_2|$  
D. $\gcd(|x_1 - x_2|, |y_1 - y_2|)$  

### 10. You need to determine if a point $C$ requires a "Left Turn" (counter-clockwise) relative to a directed vector traveling from point $A$ to point $B$. Which 2D Cross Product condition tells you this?
A. Cross Product $< 0$  
B. Cross Product $== 0$  
C. Cross Product $> 0$  
D. Cross Product is a perfect square  

## Answer Key

1. C - Comparing squared distances ($d^2$) ensures you stay entirely within integer math. Using `sqrt()` introduces floating-point precision errors that will cause your algorithm to fail on tight test cases.
2. C - A 32-bit `int` can only store values up to roughly $2 \times 10^9$. Calculating $(x_2 - x_1)^2$ when differences are $10^9$ yields $10^{18}$, causing massive overflow. You must cast your operands to `1LL` before multiplying!
3. C - Chebyshev distance is $\max(|x_1 - x_2|, |y_1 - y_2|)$. Because a diagonal move covers 1 unit of X and 1 unit of Y simultaneously, the total steps are entirely bounded by whichever axis requires the most distance.
4. B - Cross-multiplying the denominators of the slope equation prevents any possibility of dividing by zero (which causes a Runtime Error) and completely avoids floating-point precision issues.
5. B - If the rectangles do not overlap, `Right - Left` or `Top - Bottom` will be negative. Multiplying two negative bounds together creates a massive positive fake area. Clamping to $0$ safely zeroes out the area of non-overlapping rectangles.
6. D - To avoid floating-point errors from `sqrt()`, we square both sides of the Euclidean distance formula. Thus, the squared distance must be less than or equal to the *squared* radius ($r^2$).
7. A - The raw Shoelace determinant yields $2 \times \text{Area}$. If you divide by 2, an odd determinant will result in a `.5` decimal, forcing you to use `double`. Comparing $2 \times \text{Area}$ everywhere keeps you safely in the integer realm.
8. C - If a point is inside or on the boundary of the triangle, splitting the large triangle into three smaller triangles using point $P$ will yield a sum of areas exactly equal to the total area of the original triangle.
9. D - The number of integer coordinate points lying perfectly on a grid line segment is equal to the Greatest Common Divisor (GCD) of the absolute differences of the X and Y coordinates.
10. C - The 2D Cross Product calculates the determinant. If the result is strictly greater than 0 ($>0$), the orientation is Counter-Clockwise, which represents a Left Turn. If it is $<0$, it is a Right Turn (Clockwise).
