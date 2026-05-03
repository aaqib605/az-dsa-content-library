# Analyzing Code for Time Complexity

Now for the fun part: looking at actual code and figuring out its time complexity! Think of yourself as a detective. Your job is to count how many times the most deeply nested or most repeated operation runs.

Let's break down the most common patterns you'll see in the wild.

## 1. Single Loops
When you have a single loop running from $0$ to $N$, the time complexity is proportional to $N$.

```cpp
for(int i = 0; i < n; i++) {
    // This runs N times
    cout << "Hello World\n"; 
}
```
**Time Complexity:** $O(N)$

## 2. Nested Loops
When loops are nested inside each other, you **multiply** their complexities.

```cpp
for(int i = 0; i < n; i++) {
    for(int j = 0; j < n; j++) {
        // This runs N * N times
        cout << i << ", " << j << "\n";
    }
}
```
**Time Complexity:** $O(N \times N) = O(N^2)$

*But what if the inner loop doesn't go all the way up to $N$?*
```cpp
int seriesLoop(int n) {
    int count = 0;

    for (int i = n; i >= 1; i /= 2) {
        for (int j = 0; j < i; j++) {
            count++;
        }
    }

    return count;
}
```
This is an arithmetic progression summing to about $N^2/2$. We drop the constant (divide by 2), so it is still **$O(N^2)$**.

## 3. Consecutive Loops
When loops are sequential (one after the other), you **add** their complexities and then drop the lower-order terms.

```cpp
// First loop: O(N)
for(int i = 0; i < n; i++) {
    cout << "First loop\n";
}

// Second loop: O(N^2)
for(int i = 0; i < n; i++) {
    for(int j = 0; j < n; j++) {
        cout << "Second loop\n";
    }
}
```
**Total Time:** $O(N) + O(N^2) = O(N^2 + N)$. 
We drop the $N$, leaving us with:
**Time Complexity:** $O(N^2)$

## 4. Loops with Multiplication/Division Growth
Sometimes, the loop variable doesn't increase by 1 (`i++`). Instead, it doubles or halves.

```cpp
for(int i = 1; i < n; i *= 2) {
    // i goes: 1, 2, 4, 8, 16...
    cout << i << "\n";
}
```
Because the gap jumps exponentially, it reaches $N$ much faster than a normal loop. How many times can you double a number until you hit $N$? That's exactly what logarithms measure!
**Time Complexity:** $O(\log N)$

## 5. Recursive Functions
For recursion, we generally look at two things:
1. **Depth of the recursion tree:** How many times does the function call itself?
2. **Work done per call:** What happens inside each call (excluding the recursive calls)?

```cpp
void solve(int n) {
    if(n == 0) return;
    cout << "Thinking...\n"; // O(1) work
    solve(n - 1);           // Calls itself N times
}
```
Here, we make $N$ calls, and each call does $O(1)$ work.
**Time Complexity:** $O(N)$

*What about branching recursion?*
```cpp
int fibonacci(int n) {
    if(n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}
```
Each call spawns *two* more calls. The number of calls doubles at each level of depth.
**Time Complexity:** $O(2^N)$

![alt text](Images/image-4.png)

### Introducing the Master Theorem
When dealing with **Divide and Conquer** algorithms (where a problem is divided into smaller subproblems), counting the recursion depth manually can get complicated. This is where the **Master Theorem** comes in handy!

The Master Theorem provides a direct formula to solve recurrence relations of the form:
$$T(N) = aT\left(\frac{N}{b}\right) + O(N^d)$$

Where:
- **$a$**: The number of subproblems we divide into.
- **$N/b$**: The size of each subproblem.
- **$O(N^d)$**: The time spent doing work outside the recursive calls (like splitting the data or merging results).

While the full mathematical proof is complex, here are the three simplified cases you need to know:
1. **Case 1 (Work done at leaves dominates):** If $a > b^d$, the time complexity is $O(N^{\log_b a})$.
2. **Case 2 (Work is evenly distributed):** If $a = b^d$, the time complexity is $O(N^d \log N)$.
   - *Example:* Merge Sort divides the array into 2 halves ($a=2, b=2$) and merges them in linear time ($d=1$). Since $2 = 2^1$, it falls into Case 2. Complexity: $O(N^1 \log N) = O(N \log N)$.
3. **Case 3 (Work done at root dominates):** If $a < b^d$, the time complexity is $O(N^d)$.

> 💡 **Interview Insight:** You rarely need to solve complex recurrences mathematically in an interview setting. However, knowing how the Master Theorem applies to standard patterns like Merge Sort or Binary Search proves that you deeply understand how "Divide and Conquer" performance works.

## 6. Multiple Input Variables
Sometimes your code relies on two completely different inputs, say an array of size $N$ and an array of size $M$.

```cpp
void printTwoArrays(int arr1[], int n, int arr2[], int m) {
    for(int i = 0; i < n; i++) cout << arr1[i];
    for(int j = 0; j < m; j++) cout << arr2[j];
}
```
**Don't assume everything is $N$!** The time here depends on both $N$ and $M$.
**Time Complexity:** $O(N + M)$

If they were nested, it would be $O(N \times M)$.

## Common Mistakes While Analyzing Code

1. **Assuming all nested loops are $O(N^2)$**
   Look closely at the inner loop's condition. If the inner loop only runs a constant number of times (e.g., `j < 5`), the total complexity is still just $O(N)$.
   
2. **Forgetting to count built-in functions**
   In C++, hidden functions take time! For example, `std::sort()` takes $O(N \log N)$. If you put a `sort()` inside an $O(N)$ loop, your total complexity skyrockets to $O(N^2 \log N)$. Hidden functions count!

3. **Confusing Best Case with Big O**
   If you have a loop that searches for an element and `break`s when it finds it, it *could* stop on the first try. But Big O is the worst case! Assume the element is at the very end. The complexity is $O(N)$, not $O(1)$.