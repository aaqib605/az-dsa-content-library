---
title: "Queue Quiz"
slug: "queue-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your understanding of the FIFO principle, queue operations, and task scheduling concepts in competitive programming."
---

# Queue Quiz

Choose the correct answer for each question.

## Questions

### 1. Which principle exclusively defines how elements move through a Queue?

A. Last-In-First-Out (LIFO)  
B. First-In-First-Out (FIFO)  
C. Random Access (RA)  
D. Highest-Priority-First-Out (HPFO)  

### 2. When interacting with a standard Queue, where are new elements inserted, and where are existing elements removed?

A. Inserted at the Front, Removed from the Front  
B. Inserted at the Back, Removed from the Back  
C. Inserted at the Back, Removed from the Front  
D. Inserted at the Front, Removed from the Back  

### 3. What is the exact Time Complexity of the `push()`, `pop()`, `front()`, and `back()` operations on a Queue?

A. $O(N)$  
B. $O(\log N)$  
C. $O(N \log N)$  
D. $O(1)$  

### 4. Which of the following is a classic, real-world application of the Queue data structure?

A. CPU Task Scheduling (giving the processor to the oldest waiting app)  
B. The "Undo" button in Microsoft Word  
C. Tracking the directory path you took to find a specific file  
D. The "Back" button on your web browser  

### 5. In the classic "Number of Recent Calls" problem, you track pings that happened in the last 3000ms. Why do we `pop()` elements from the Queue?

A. To clear space in memory so the program doesn't crash  
B. To enforce the "Oldest Data Expires First" rule, removing pings that fell behind the $t - 3000$ window  
C. To find the minimum ping time  
D. To reverse the order of the pings  

## Answer Key

1. B - A Queue operates strictly on the First-In-First-Out (FIFO) principle. The first element to join the line is the first element to be served and removed.
2. C - To maintain fairness, you must enqueue (push) new elements to the absolute Back of the line, and dequeue (pop) elements exclusively from the Front of the line.
3. D - By restricting access to just the front and back pointers, all core Queue operations are instantaneous, executing in exactly $O(1)$ time complexity.
4. A - A CPU uses a Queue to manage tasks. The task that has been waiting the longest gets processed next, guaranteeing fairness. B, C, and D are all perfect examples of a Stack (LIFO).
5. B - As time moves forward, the oldest pings expire and become useless. Because a Queue processes the oldest data first, we can simply `pop()` from the front until the oldest ping is safely within our 3000ms time frame!
