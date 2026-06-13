<VIDEO_WIDGET>

<VIDEO_ID>3454</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# The Call Stack

## Call Stack Intuition

In the previous lesson, we learned that a recursive function calls itself to solve smaller sub-problems. But how exactly does the computer keep track of all these nested function calls?

To understand recursion deeply, you must understand the **Call Stack**. The call stack is like a stack of plates. When you call a function, the computer puts a new "plate" (a memory frame) on top of the stack. When the function finishes, the computer takes that "plate" off.

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/01ea6f38-1fab-40c6-82cf-e85e8ca3d8cc.png" alt="Recursion Call Stack" style="max-width: 100%; height: auto;" identifier="az-img-upload">

Let's trace `sayHello(3)`:

1. `sayHello(3)` is called. A frame is added to the stack. `times = 3`. It prints "Hello!" and calls `sayHello(2)`.
2. `sayHello(2)` is called. A new frame is placed **on top**. `times = 2`. It prints "Hello!" and calls `sayHello(1)`.
3. `sayHello(1)` is called. Another frame is placed on top. `times = 1`. It prints "Hello!" and calls `sayHello(0)`.
4. `sayHello(0)` is called. The base case `times == 0` is true! The function hits `return`. The frame for `sayHello(0)` is popped off the stack.
5. Control goes back to `sayHello(1)`, which has no more code to run, so it pops off.
6. Control goes back to `sayHello(2)`, which pops off.
7. Control goes back to `sayHello(3)`, which pops off. The stack is empty, and the program ends.

> 💡 **Interview Insight: Auxiliary Space & Constraints**
> Understanding the call stack is critical because **every frame added to the stack takes up physical memory**.
>
> - **Space Complexity:** If `sayHello(N)` calls itself $N$ times, the maximum depth of the tree is $N$. This means the **Auxiliary Space Complexity is $O(N)$**. Beginners often mistake recursion for $O(1)$ space because they didn't explicitly allocate an array, but the call stack _is_ an array!
> - **System Constraints:** A typical C++ program allocates a limited amount of stack memory (often around 8MB). If a recursive function goes deeper than roughly $10^5$ calls, it triggers a `Segmentation Fault` or `Stack Overflow`. When you see $N \le 10^5$ in a problem description, know that an $O(N)$ depth recursive approach is pushing the physical limits of the stack!

---

## Dry Run of Recursive Functions

"Dry running" means tracing the code on paper step by step. Let's practice with a slightly different printing example.

### Printing Using Recursion

What happens if we swap the order of the recursive call and the print statement?

```cpp
void printNumbers(int n) {
    if (n == 0) {
        return; // Base Case
    }

    printNumbers(n - 1); // Recursive Call FIRST
    cout << n << " ";    // Print LATER
}
```

If we call `printNumbers(3)`, what is the output? Let's dry run:

1. `printNumbers(3)`: calls `printNumbers(2)`. (It _waits_ to print).
2. `printNumbers(2)`: calls `printNumbers(1)`. (It _waits_ to print).
3. `printNumbers(1)`: calls `printNumbers(0)`. (It _waits_ to print).
4. `printNumbers(0)`: Base case hit! Returns.
5. Back in `printNumbers(1)`: It finishes waiting, executes `cout << 1 << " "`. Returns.
6. Back in `printNumbers(2)`: It finishes waiting, executes `cout << 2 << " "`. Returns.
7. Back in `printNumbers(3)`: It finishes waiting, executes `cout << 3 << " "`. Returns.

**Output:** `1 2 3`

This is the magic of recursion! By changing where we put the recursive call, we reversed the order of printing without using any loops.

---

## Returning Values from Recursion

Often, recursive functions don't just print things; they calculate and return values. Let's look at simple recursion with numbers.

### Simple Recursion with Numbers (Factorial)

The factorial of a number $N$ (written as $N!$) is the product of all positive integers less than or equal to $N$.
Example: $4! = 4 \times 3 \times 2 \times 1 = 24$.

Notice that $4! = 4 \times (3 \times 2 \times 1) = 4 \times 3!$.
This gives us a perfect recursive relationship: `factorial(N) = N * factorial(N - 1)`.

```cpp
int factorial(int n) {
    // Base case: 0! is 1 (and 1! is 1)
    if (n == 0 || n == 1) {
        return 1; // **RETURN base case**
    }

    // Recursive case
    int smallerAnswer = factorial(n - 1);
    return n * smallerAnswer;
}
```

Let's trace `factorial(3)`:

- `factorial(3)` needs `factorial(2)`.
- `factorial(2)` needs `factorial(1)`.
- `factorial(1)` returns `1` (Base case).
- `factorial(2)` receives `1`, returns `2 * 1 = 2`.
- `factorial(3)` receives `2`, returns `3 * 2 = 6`.

**Visualizing the Return (Bubbling Up):**

```text
f(3) -> waits for f(2)
      f(2) -> waits for f(1)
            f(1) -> returns 1
      f(2) <- receives 1, returns 2 * 1 = 2
f(3) <- receives 2, returns 3 * 2 = 6
```

> 💡 **Interview Insight:** When writing recursive functions that compute and return values, a very common mistake is omitting the `return` keyword before the recursive call. Always ensure that the computed value is explicitly returned up the call chain!

### The Recurrence Relation

Once you understand how the recursion builds up, you can express its time complexity mathematically. For `factorial(N)`, the time to solve for $N$ is the time to solve for $N-1$ plus the $O(1)$ multiplication step.
This gives us a **Recurrence Relation**:
$$T(N) = T(N-1) + O(1)$$
Because we do an $O(1)$ operation $N$ times, this relation simplifies to a final Time Complexity of $O(N)$.

</READING_WIDGET>
