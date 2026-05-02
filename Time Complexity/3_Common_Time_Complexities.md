# Common Time Complexities

Now that we know what Big O is and how to clean it up, let's look at the "Big O Hall of Fame." These are the most common time complexities you will see in coding interviews and competitive programming. 

We will list them from **fastest** to **slowest**.

## 1. $O(1)$ - Constant Time (The Dream)
No matter how massive the input is, the algorithm takes the exact same amount of time.
- **Example:** Accessing an element in an array by its index, or doing basic math operations.
```cpp
int getFirstElement(int arr[]) {
    return arr[0]; // Instant, regardless of array size!
}
```

### 🌟 Special Mention: Amortized Time Complexity
Sometimes, an operation might take $O(N)$ time once in a while, but $O(1)$ time in almost all other cases. When we average out the heavy operation over a sequence of many operations, the cost becomes constant. We call this **Amortized $O(1)$**.

- **Classic Example:** `std::vector::push_back()` in C++. 
When you push elements into a vector, it takes $O(1)$ time. But when the vector runs out of underlying memory, it creates a new array double the size and copies all $N$ elements over ($O(N)$ time). However, because this doubling happens so rarely, the *average* cost of a single push is mathematically proven to be $O(1)$. 

> 💡 **Interview Insight:** Interviewers love asking, *"What is the time complexity of pushing to a dynamic array?"* If you just say $O(1)$, they might penalize you. The golden answer is: *"It is $O(1)$ **amortized**, but $O(N)$ in the worst-case when the array resizes."*

## 2. $O(\log N)$ - Logarithmic Time (Extremely Fast)
If $N$ doubles, the number of operations only increases by 1! This usually happens when you divide the search space in half each step.
- **Example:** Binary Search. 
- **Mind-blowing fact:** If you have $1,000,000$ items, it takes about 20 steps to find your target. If you have $1,000,000,000$ (1 billion) items, it only takes about 30 steps!
```cpp
// Searching in a sorted array by halving the search space
int l = 0, r = n - 1;
while(l <= r) {
    int mid = l + (r - l) / 2;
    if(arr[mid] == target) return mid;
    if(arr[mid] < target) l = mid + 1;
    else r = mid - 1;
}
```

## 3. $O(N)$ - Linear Time (Fair & Steady)
The time taken grows directly with the input size. If $N$ is 100, you do 100 operations.
- **Example:** Looping through an array to find the maximum value.
```cpp
int maxVal = arr[0];
for(int i = 1; i < n; i++) {
    maxVal = max(maxVal, arr[i]);
}
```

## 4. $O(N \log N)$ - Linearithmic Time (The Sorting Standard)
This is slightly slower than $O(N)$ but much faster than $O(N^2)$. It usually happens when you split data in half recursively and then merge or process it.
- **Example:** Efficient sorting algorithms like Merge Sort, Quick Sort, and C++'s built-in `std::sort()`.

## 5. $O(N^2)$ - Quadratic Time (Use with Caution)
The time taken is the square of the input size. If $N = 1,000$, operations = $1,000,000$. This is generally the limit for inputs around $10^4$.
- **Example:** Nested loops, checking all pairs in an array (like Bubble Sort or Selection Sort).
```cpp
for(int i = 0; i < n; i++) {
    for(int j = 0; j < n; j++) {
        // Checking pair (i, j)
    }
}
```

## 6. $O(2^N)$ - Exponential Time (Danger Zone)
The number of operations doubles with each new element added to the input. This is terribly slow and usually only works if $N \le 20$.
- **Example:** Finding all subsets of a set, or a simple recursive Fibonacci function without memory (memoization).

## 7. $O(N!)$ - Factorial Time (Game Over)
The absolute slowest. If $N=10$, it's 3.6 million operations. If $N=12$, it's 479 million operations.
- **Example:** Finding all permutations of a string.

![alt text](Images/image-3.png)

<!-- > **[IMAGE PLACEHOLDER]**
> **Image Content:** A "Big O Cheat Sheet" graph plotting all these complexities on one chart. The X-axis is 'Elements', Y-axis is 'Operations'. $O(1)$ and $O(\log N)$ should be in a green "Excellent" zone at the bottom. $O(N)$ and $O(N \log N)$ in a yellow "Fair" zone. $O(N^2)$, $O(2^N)$, and $O(N!)$ shooting aggressively up into a red "Horrible" zone.
> **Location:** Insert here, at the end of the section as a visual summary. -->