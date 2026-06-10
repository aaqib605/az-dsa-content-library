<READING_WIDGET>

# Time Complexity Quiz

</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does time complexity describe?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Time complexity does not measure actual wall-clock time because that depends on hardware.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Time complexity describes how the runtime of an algorithm scales or grows relative to the size of the input. It is independent of the hardware running the code.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The exact number of seconds a program takes to run
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                How the runtime of an algorithm grows as input size increases
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The amount of memory used by the input array
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number of lines in a program
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Time Complexity, Big O, Basics
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which time complexity is generally the fastest?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Look for the complexity that implies the runtime doesn't change regardless of input size.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        $O(1)$ means the runtime is constant and does not grow with the input size $N$. It is the fastest possible time complexity.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N \log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Big O, Complexity Order
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the simplified Big O complexity of $T(N) = 5N^2 + 100N + 20$?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        In Big O notation, we drop constants and only keep the term that grows the fastest.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        In Big O notation, we ignore constant multipliers and lower-order terms because for very large $N$, the highest degree term dominates the runtime. Thus, $5N^2 + 100N + 20$ simplifies to $O(N^2)$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(5N^2 + 100N + 20)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2 + N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Big O, Mathematical Simplification
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the time complexity of this code?**
```cpp
for (int i = 0; i < n; i++) {
    cout << arr[i] << "\n";
}
```
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        The loop runs from 0 to $n-1$, incrementing by 1 each time.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The loop iterates exactly $N$ times. Inside the loop, printing takes $O(1)$ time. Thus, the total time complexity is $O(N)$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(\log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Loops, Code Analysis
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the time complexity of this code?**
```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        cout << i << " " << j << "\n";
    }
}
```
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about how many times the inner print statement runs relative to $n$.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The outer loop runs $N$ times. For every iteration of the outer loop, the inner loop also runs $N$ times. Therefore, the total number of iterations is $N \times N = N^2$, making the time complexity $O(N^2)$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N + N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N \log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Nested Loops, Code Analysis
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the time complexity of this loop?**
```cpp
for (int i = 1; i < n; i *= 2) {
    cout << i << "\n";
}
```
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        The loop variable $i$ doubles in every step instead of increasing by 1.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Because $i$ multiplies by 2 on each iteration, it reaches $n$ extremely fast. The number of iterations needed for $2^k$ to reach $n$ is $k = \log_2 N$. Thus, the time complexity is $O(\log N)$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(\log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Logarithmic Complexity, Loops
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If an algorithm checks every possible pair in an array of size $N$, what is its typical time complexity?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        How many pairs exist in an array of size $N$?
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The number of pairs in an array of size $N$ is roughly $N \times N / 2$. Since we ignore constants in Big O notation, the time complexity of checking every pair is $O(N^2)$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(\log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Pairs, Combinatorics
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **A C++ solution has $N = 10^5$ and uses an $O(N^2)$ algorithm for a 1-second time limit. Based on the $10^8$ operations rule, what is most likely to happen?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Calculate $(10^5)^2$ and compare it to the standard $10^8$ operations per second limit.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        An $O(N^2)$ algorithm for $N = 10^5$ will perform approximately $(10^5)^2 = 10^{10}$ operations. A standard C++ program performs roughly $10^8$ operations in 1 second. $10^{10}$ is much greater than $10^8$, so the program will receive a Time Limit Exceeded (TLE) error.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will pass easily
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will probably get Time Limit Exceeded (TLE)
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will use no extra memory
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will become $O(N \log N)$ automatically
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        TLE, Constraints, Magic Number
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the time complexity of searching for a value in a sorted array using binary search?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Binary search cuts the search space in half at every step.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Binary search repeatedly halves the number of elements it needs to search. This process of repeated halving leads to a time complexity of $O(\log N)$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(\log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Binary Search, Logarithmic Complexity
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In interviews, when someone asks for "space complexity", they usually mean:**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Space complexity tracks the extra memory created specifically by your algorithm.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Space complexity refers to the auxiliary (extra) memory used by your algorithm, excluding the space taken by the inputs themselves.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The exact RAM size of the computer
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number of input elements only
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The extra memory used by the algorithm (auxiliary space)
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The total runtime of the program
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Space Complexity, Auxiliary Space
    </MCQ_TAGS>
</MCQ_WIDGET>
