---
title: "Basic Recursion Quiz"
slug: "basic-recursion-quiz"
track: "beginner-dsa"
level: "Mixed"
order: 1
status: "Draft"
description: "Practice quiz covering recursion fundamentals, base cases, the call stack, space complexity, and C++ reference traps."
---

# Basic Recursion Quiz

Choose the correct answer for each question.

## Questions

### 1. What is the fundamental concept of recursion in programming?

A. Using a `for` loop to repeat a task indefinitely  
B. A function that calls another completely different function  
C. A function that calls itself to solve smaller instances of the same problem  
D. A built-in feature to prevent syntax errors  

### 2. What happens if a recursive function does not have a base case?

A. The function will execute normally but run faster  
B. The compiler will automatically add one for you  
C. The function will skip execution entirely  
D. It will lead to infinite recursion and eventually crash with a Stack Overflow  

### 3. Which of the following best describes the "base case" in a recursive function?

A. The part of the code where the function actually calls itself  
B. The condition under which the function stops calling itself  
C. The very first function call made from `main()`  
D. A variable used to track the number of loops  

### 4. Which underlying data structure does the computer use to keep track of active recursive function calls?

A. Queue  
B. Hash Map  
C. Linked List  
D. Stack (The Call Stack)  

### 5. Look at the following code snippet. If we call `printDesc(3)`, what will be the exact output?

```cpp
void printDesc(int n) {
    if (n == 0) return;
    cout << n << " ";
    printDesc(n - 1);
}
```

A. `1 2 3`  
B. `3 2 1`  
C. `3 2 1 0`  
D. It will cause an infinite loop  

### 6. Look at the following code snippet. If we call `printAsc(3)`, what will be the exact output?

```cpp
void printAsc(int n) {
    if (n == 0) return;
    printAsc(n - 1);
    cout << n << " ";
}
```

A. `1 2 3`  
B. `3 2 1`  
C. `0 1 2 3`  
D. Nothing will be printed  

### 7. What is the Auxiliary Space Complexity of a recursive function that goes exactly $N$ levels deep into the call stack?

A. $O(1)$  
B. $O(\log N)$  
C. $O(N)$  
D. $O(N^2)$  

### 8. Why is it dangerous to pass large data structures like `std::vector` by value in a recursive function?

A. It causes syntax errors in C++  
B. It reverses the order of the vector elements automatically  
C. It creates a deep copy at every stack frame, drastically increasing time and space complexity to $O(N^2)$  
D. It forces the recursive function to skip the base case  

### 9. If a typical C++ program has an 8MB stack memory limit, roughly what is the maximum safe recursion depth before triggering a Segmentation Fault?

A. $10$ calls  
B. $1,000$ calls  
C. $10^5$ calls  
D. $10^8$ calls  

### 10. For a recursive function solving a problem of size $N$, if its recurrence relation is $T(N) = T(N-1) + O(1)$, what is the simplified final Time Complexity?

A. $O(1)$  
B. $O(\log N)$  
C. $O(N)$  
D. $O(N^2)$  

## Answer Key

1. C - Recursion occurs when a function calls itself, breaking a problem down into smaller, identical sub-problems until a base case is reached.
2. D - Without a base case to stop the recursion, the function will call itself infinitely, quickly filling up the call stack and crashing the program with a Stack Overflow.
3. B - The base case is the halting condition. It tells the recursive function that the problem is small enough to be solved directly without further recursive calls.
4. D - The computer uses the Call Stack (a stack data structure) to keep track of function execution contexts (frames), pushing a frame when a function is called and popping it when it returns.
5. B - The `cout` statement happens *before* the recursive call. Therefore, it prints the current value of $n$ (3, then 2, then 1) before moving deeper into the recursion.
6. A - Because the `cout` statement happens *after* the recursive call returns, the function reaches the base case first (0), then prints as it bubbles back up the stack: 1, then 2, then 3.
7. C - Every active recursive call adds a frame to the call stack. If the recursion goes $N$ levels deep, it occupies $N$ frames, leading to $O(N)$ Auxiliary Space Complexity.
8. C - Passing by value (`vector<int> arr`) means C++ makes a complete deep copy of the entire vector for every single recursive call, resulting in an $O(N^2)$ Memory Limit Exceeded (MLE) disaster. Always use reference (`vector<int>& arr`)!
9. C - A typical 8MB stack memory can hold roughly $10^5$ standard function frames before running out of space, which triggers a Stack Overflow (Segmentation Fault).
10. C - Doing an $O(1)$ operation $N$ times means the total time taken is proportional to $N$, giving a final Time Complexity of $O(N)$.
