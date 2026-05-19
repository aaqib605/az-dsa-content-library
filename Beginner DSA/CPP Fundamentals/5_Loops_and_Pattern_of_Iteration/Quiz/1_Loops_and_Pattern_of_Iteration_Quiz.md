---
title: "Loops and Pattern of Iteration Quiz"
slug: "loops-and-pattern-of-iteration-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on for-loops, while-loops, break, continue, and iteration control!"
---

# Loops and Pattern of Iteration Quiz

Test your understanding of iteration and loop control in C++!

---

### 1. In a standard `for` loop `for (int i = 0; i < 10; i++)`, how many times will the loop execute?
A. 9  
B. 10  
C. 11  
D. Infinite  

### 2. What is the primary difference between a `while` loop and a `do-while` loop?
A. `while` loops are faster.  
B. `do-while` loops do not need a condition.  
C. A `do-while` loop is guaranteed to execute at least once, even if the condition is false from the start.  
D. `while` loops can only be used for counting.  

### 3. What does the `break;` statement do inside a loop?
A. It skips the current iteration and jumps to the next one.  
B. It pauses the program for 1 second.  
C. It immediately destroys the loop entirely and continues executing the code after the loop.  
D. It restarts the loop from the beginning.  

### 4. What does the `continue;` statement do inside a loop?
A. It skips the rest of the code in the current iteration and instantly moves to the next iteration.  
B. It ignores any errors and keeps the loop running.  
C. It acts exactly the same as `break;`.  
D. It stops the loop from timing out.  

### 5. What happens if you run this code?
```cpp
while (true) {
    cout << "Hello!\n";
}
```
A. It prints "Hello!" once.  
B. It prints "Hello!" 100 times and stops.  
C. It causes a Compilation Error.  
D. It creates an Infinite Loop and prints "Hello!" forever until the program is killed or crashes.  

### 6. You have a nested loop: an outer loop that runs $N$ times, and an inner loop that runs $M$ times. How many times does the innermost code execute?
A. $N + M$ times.  
B. $N \times M$ times.  
C. $\max(N, M)$ times.  
D. $N^M$ times.  

### 7. What is the correct C++11 syntax to iterate over every element in a container called `primes` using a Range-Based For Loop?
A. `for (int x in primes)`  
B. `for (int x : primes)`  
C. `for x of primes`  
D. `foreach (int x : primes)`  

### 8. What is the standard Time Complexity of a single loop that runs from `0` to `N`?
A. $O(1)$  
B. $O(\log N)$  
C. $O(N)$  
D. $O(N^2)$  

### 9. If you nest three loops, each running from $0$ to $N$, what is the total Time Complexity?
A. $O(3N)$  
B. $O(N^3)$  
C. $O(N \log N)$  
D. $O(\log^3 N)$  

### 10. Which of the following loop conditions will eventually terminate assuming `N > 0`?
A. `while (N > 0) { N++; }`  
B. `for (int i = 0; i < N; i--)`  
C. `while (N > 0) { N /= 2; }`  
D. `while (true) {}`  

---

## Answer Key

1. **B** (It starts at 0 and stops when `i` reaches 10, meaning it runs for 0, 1, 2, ..., 9, which is 10 times).
2. **C** (A `do-while` loop evaluates its condition *after* the body executes, guaranteeing at least one run).
3. **C** (`break` acts as an emergency exit, breaking out of the innermost loop completely).
4. **A** (`continue` just skips the current cycle, useful for bypassing specific elements like negative numbers).
5. **D** (`true` is always true, so the loop has no exit condition. This will cause a Time Limit Exceeded (TLE) error on Online Judges!).
6. **B** (For every 1 iteration of the outer loop, the inner loop runs $M$ times. So $N \times M$ total).
7. **B** (`for (int x : primes)` is the clean, modern way to iterate through collections).
8. **C** (A single loop over $N$ items runs in linear time, $O(N)$).
9. **B** (Nested loops multiply their complexities. $N \times N \times N = N^3$).
10. **C** (Dividing $N$ by 2 repeatedly will eventually make it reach 0 (due to integer division), breaking the loop condition!).
