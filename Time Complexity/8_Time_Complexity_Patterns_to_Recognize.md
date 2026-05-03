# Time Complexity Patterns to Recognize

As you solve more and more problems, you'll start to notice that certain time complexities almost always pair up with specific algorithms or data structures. Recognizing these patterns is like developing a "sixth sense" for coding!

Here is a quick cheat sheet of patterns you should instantly recognize:

## 1. $O(N)$ - Loop over the array
Whenever you need to look at every element in an array exactly once (or a constant number of times), you are looking at an $O(N)$ pattern.
- **Classic Examples:** Finding the maximum element, calculating the sum of an array, Two-Pointer approach (where both pointers only move in one direction), Sliding Window technique.

## 2. $O(N^2)$ - Nested loops over the array
If you need to compare every element with *every other element*, you will likely write a loop inside a loop, leading to an $O(N^2)$ pattern.
- **Classic Examples:** Bubble Sort, Insertion Sort, generating all possible sub-arrays, checking all pairs to find a specific sum (the brute-force way).

## 3. $O(\log N)$ - Binary Search
If the data is **sorted**, and you are dividing the search space in half at every step, your brain should immediately yell "$O(\log N)$!" 
- **Classic Examples:** Binary Search, searching in a balanced Binary Search Tree (BST), calculating $x^n$ using fast exponentiation.

## 4. $O(N \log N)$ - Sorting
If you ever call a built-in sorting function, or implement a "Divide and Conquer" algorithm that does linear work at each level of division, you have an $O(N \log N)$ pattern.
- **Classic Examples:** `std::sort()` in C++, Merge Sort, Quick Sort. 

## 5. $O(2^N)$ - Pick or Don't Pick (Subsets)
If at every step you have two choices (e.g., "Do I include this element in my subset, or do I exclude it?"), you are generating a recursion tree where every branch splits into two. This is the hallmark of $O(2^N)$ exponential growth.
- **Classic Examples:** Generating all subsets (Power Set), the naive recursive Knapsack problem, classic recursive Fibonacci.

## 6. $O(N!)$ - Permutations
If you need to explore every possible *arrangement* or *order* of a set of items, you are dealing with Factorial time. 
- **Classic Examples:** Generating all permutations of a string, solving the Traveling Salesperson Problem (brute force).

> 💡 **Interview Insight:** In interviews, if you are stuck, try to work backward from these patterns. If the array is sorted, ask yourself: *"Can I use Binary Search here to get an $O(\log N)$ runtime?"* If the constraint is unusually small like $N \le 20$, ask yourself: *"Does the interviewer want a 'Pick or Don't Pick' $O(2^N)$ recursion here?"*
