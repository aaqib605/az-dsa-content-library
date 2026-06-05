---
title: "Stack Quiz"
slug: "stack-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your understanding of the LIFO principle, the core O(1) stack operations, and common CP pitfalls."
---

# Stack Quiz

Choose the correct answer for each question.

## Questions

### 1. Which principle defines the behavior of a Stack data structure?

A. First-In-First-Out (FIFO)  
B. Last-In-First-Out (LIFO)  
C. First-In-Last-Out (FILO)  
D. Both B and C  

### 2. What is the exact Time Complexity of the `push()`, `pop()`, and `top()` operations on a standard Stack?

A. $O(N)$  
B. $O(\log N)$  
C. $O(N \log N)$  
D. $O(1)$  

### 3. In C++, what happens if you attempt to call `st.pop()` or `st.top()` on a Stack that is completely empty?

A. The program silently ignores the command and continues running  
B. The stack automatically returns `0` or `null`  
C. The program crashes with a fatal Segmentation Fault  
D. The stack resets its size to `-1`  

### 4. Which of the following real-world systems behaves exactly like a Stack?

A. A line of customers waiting at a grocery store checkout  
B. The "Undo" button (Ctrl+Z) in a text editor  
C. A printer queue handling multiple document requests  
D. Cars waiting at a toll booth  

### 5. Why is a Stack the perfect data structure for solving the classic "Valid Parentheses" problem (e.g., `s = "([])"`)?

A. Because the string is read from right to left  
B. Because you need to match the most recently opened bracket first, which perfectly mirrors LIFO  
C. Because it sorts the brackets alphabetically in $O(1)$ time  
D. Because stacks can automatically detect syntax errors in C++  

### 6. Mathematically, what does the `.size()` operation return when called on a Stack?

A. The total memory allocated for the stack in bytes  
B. The value of the element currently resting at the top of the stack  
C. The maximum capacity the stack is allowed to reach  
D. The total number of elements currently stored inside the stack  

## Answer Key

1. D - Both Last-In-First-Out (LIFO) and First-In-Last-Out (FILO) describe the exact same behavior: the element that goes in last is the first one out, and the element that goes in first is trapped at the bottom until the very end.
2. D - Because a Stack restricts all access to a single point (the top), it doesn't have to search or shift elements. Every core operation is instantaneous, operating in exactly $O(1)$ time.
3. C - Trying to access or remove the top element of an empty stack accesses restricted memory, causing the OS to instantly terminate your program with a Segmentation Fault. Always use `if (!st.empty())`!
4. B - Every time you type a word, it is "pushed" to the stack. When you hit Undo, the most recently typed word is "popped" and removed, restoring the previous state underneath it.
5. B - The "Inside-Out" matching rule (where `[` must be closed by `]` before the outer `(` can be closed) demands that we process the most recently seen items first. This is exactly what a Stack does.
6. D - The `.size()` function simply returns the integer count of how many items are currently residing in the stack structure.
