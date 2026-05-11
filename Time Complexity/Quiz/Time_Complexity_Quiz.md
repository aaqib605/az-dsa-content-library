---
title: "Time Complexity Quiz"
slug: "time-complexity-quiz"
track: "beginner-dsa"
level: "Mixed"
order: 1
status: "Draft"
description: "Practice quiz covering Big O notation, code analysis, common complexities, constraints, and time-space trade-offs."
---

# Time Complexity Quiz

Choose the correct answer for each question.

## Questions

### 1. What does time complexity describe?

A. The exact number of seconds a program takes to run  
B. How the runtime of an algorithm grows as input size increases  
C. The amount of memory used by the input array  
D. The number of lines in a program  

### 2. Which time complexity is generally the fastest?

A. $O(1)$  
B. $O(N)$  
C. $O(N \log N)$  
D. $O(N^2)$  

### 3. What is the simplified Big O complexity of $T(N) = 5N^2 + 100N + 20$?

A. $O(5N^2 + 100N + 20)$  
B. $O(N^2 + N)$  
C. $O(N^2)$  
D. $O(N)$  

### 4. What is the time complexity of this code?

```cpp
for (int i = 0; i < n; i++) {
    cout << arr[i] << "\n";
}
```

A. $O(1)$  
B. $O(\log N)$  
C. $O(N)$  
D. $O(N^2)$  

### 5. What is the time complexity of this code?

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        cout << i << " " << j << "\n";
    }
}
```

A. $O(N)$  
B. $O(N + N)$  
C. $O(N \log N)$  
D. $O(N^2)$  

### 6. What is the time complexity of this loop?

```cpp
for (int i = 1; i < n; i *= 2) {
    cout << i << "\n";
}
```

A. $O(1)$  
B. $O(\log N)$  
C. $O(N)$  
D. $O(N^2)$  

### 7. If an algorithm checks every possible pair in an array of size $N$, what is its typical time complexity?

A. $O(1)$  
B. $O(\log N)$  
C. $O(N)$  
D. $O(N^2)$  

### 8. A C++ solution has $N = 10^5$ and uses an $O(N^2)$ algorithm for a 1-second time limit. Based on the $10^8$ rule, what is most likely to happen?

A. It will pass easily  
B. It will probably get Time Limit Exceeded  
C. It will use no extra memory  
D. It will become $O(N \log N)$ automatically  

### 9. What is the time complexity of searching for a value in a sorted array using binary search?

A. $O(1)$  
B. $O(\log N)$  
C. $O(N)$  
D. $O(N^2)$  

### 10. In interviews, when someone asks for "space complexity", they usually mean:

A. The exact RAM size of the computer  
B. The number of input elements only  
C. The extra memory used by the algorithm  
D. The total runtime of the program  

## Answer Key

1. B
2. A
3. C
4. C
5. D
6. B
7. D
8. B
9. B
10. C
