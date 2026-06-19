<READING_WIDGET>
# Basic Geometry Quiz

Choose the correct answer for each question.
</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the safest way to compare the Euclidean distance between points in competitive programming?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Comparing squared distances ($d^2$) ensures you stay entirely within integer math. Using `sqrt()` introduces floating-point precision errors that will cause your algorithm to fail on tight test cases.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Always use `sqrt()` and store the result in a `double`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Use `sqrt()` but cast the result back to an `int`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Avoid `sqrt()` entirely and compare the squared integer distances ($d^2$)
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Use the Manhattan distance formula instead as an approximation
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **When calculating squared Euclidean distance, if the coordinates can reach up to $10^9$, what critical C++ trap must you avoid?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        A 32-bit `int` can only store values up to roughly $2 \times 10^9$. Calculating $(x_2 - x_1)^2$ when differences are $10^9$ yields $10^{18}$, causing massive overflow. You must cast your operands to `1LL` before multiplying!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The numbers will exceed the `long long` limit, so you must use BigInt
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `sqrt()` will return a negative number
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $(10^9)^2 = 10^{18}$, which overflows a standard 32-bit `int`, so you must cast to a 64-bit `long long`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Squared distances are always perfectly safe and never overflow
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If a character can move one step horizontally, vertically, OR diagonally, which distance metric perfectly describes the minimum steps required to reach a target?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Chebyshev distance is $\max(|x_1 - x_2|, |y_1 - y_2|)$. Because a diagonal move covers 1 unit of X and 1 unit of Y simultaneously, the total steps are entirely bounded by whichever axis requires the most distance.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Euclidean Distance
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Manhattan Distance
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Chebyshev Distance (Chess King Distance)
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Minkowski Distance
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the mathematically robust way to check if three points $A, B, C$ are collinear without using slope division?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Cross-multiplying the denominators of the slope equation prevents any possibility of dividing by zero (which causes a Runtime Error) and completely avoids floating-point precision issues.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $\frac{y_2 - y_1}{x_2 - x_1} == \frac{y_3 - y_2}{x_3 - x_2}$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $(y_2 - y_1) \times (x_3 - x_2) == (y_3 - y_2) \times (x_2 - x_1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $\max(|x_1-x_2|, |y_1-y_2|) == \max(|x_2-x_3|, |y_2-y_3|)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Check if their Euclidean distances sum up perfectly using `sqrt()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **You are finding the overlap of two axis-aligned rectangles using the Min-Max Boundary Trick. Why is it absolutely necessary to clamp the width and height to $0$ using `max(0LL, right - left)`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        If the rectangles do not overlap, `Right - Left` or `Top - Bottom` will be negative. Multiplying two negative bounds together creates a massive positive fake area. Clamping to $0$ safely zeroes out the area of non-overlapping rectangles.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                To ensure the area doesn't overflow a 32-bit integer
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Because multiplying a negative width by a negative height (when they don't overlap) mathematically creates a fake positive area
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                To automatically cast the numbers to `long long`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It is not necessary; negative dimensions are fine in CP
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which equation correctly and safely checks if a point $(x, y)$ is strictly inside or on the boundary of a circle with center $(h, k)$ and radius $r$?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        To avoid floating-point errors from `sqrt()`, we square both sides of the Euclidean distance formula. Thus, the squared distance must be less than or equal to the *squared* radius ($r^2$).
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $\sqrt{(x-h)^2 + (y-k)^2} \le r$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $|x - h| + |y - k| \le r$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $(x - h)^2 + (y - k)^2 \le r$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $(x - h)^2 + (y - k)^2 \le r^2$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Why do CP templates for the Shoelace Formula typically calculate and compare $2 \times \text{Area}$ instead of just the Area itself?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The raw Shoelace determinant yields $2 \times \text{Area}$. If you divide by 2, an odd determinant will result in a `.5` decimal, forcing you to use `double`. Comparing $2 \times \text{Area}$ everywhere keeps you safely in the integer realm.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Dividing by 2 introduces `.5` decimal values, requiring floats. Keeping it as $2 \times \text{Area}$ ensures the math remains in pure integers.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Because the Shoelace formula inherently calculates exactly double the area and it's impossible to divide it.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                To prevent negative area values from occurring.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $2 \times \text{Area}$ is a requirement for Pick's Theorem.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **According to the Area Sum Method, a point $P$ is inside a triangle $ABC$ if:**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        If a point is inside or on the boundary of the triangle, splitting the large triangle into three smaller triangles using point $P$ will yield a sum of areas exactly equal to the total area of the original triangle.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The Shoelace area of $PAB$ is zero
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The Cross Product of $PA$ and $PB$ is strictly positive
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $2\times\text{Area}(ABC) == 2\times\text{Area}(PAB) + 2\times\text{Area}(PBC) + 2\times\text{Area}(PCA)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The Manhattan distance from $P$ to the centroid is minimized
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Using Pick's Theorem ($\text{Area} = I + \frac{B}{2} - 1$), you need to find the number of integer boundary points $B$ on a line segment between $(x_1, y_1)$ and $(x_2, y_2)$. Which mathematical function provides the exact number of points?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The number of integer coordinate points lying perfectly on a grid line segment is equal to the Greatest Common Divisor (GCD) of the absolute differences of the X and Y coordinates.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $\min(|x_1 - x_2|, |y_1 - y_2|)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $\max(|x_1 - x_2|, |y_1 - y_2|)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $|x_1 - x_2| \times |y_1 - y_2|$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $\gcd(|x_1 - x_2|, |y_1 - y_2|)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **You need to determine if a point $C$ requires a "Left Turn" (counter-clockwise) relative to a directed vector traveling from point $A$ to point $B$. Which 2D Cross Product condition tells you this?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The 2D Cross Product calculates the determinant. If the result is strictly greater than 0 ($>0$), the orientation is Counter-Clockwise, which represents a Left Turn. If it is $<0$, it is a Right Turn (Clockwise).
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Cross Product $< 0$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Cross Product $== 0$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Cross Product $> 0$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Cross Product is a perfect square
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Basic Geometry, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>
