---
title: "C++ Fundamentals Quiz"
slug: "cpp-fundamentals-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 12
status: "Draft"
duration: ""
updatedAt: "2026-05-15"
description: "Test your knowledge of C++ Fundamentals including data types, loops, vectors, sorting, and memory management!"
---

# C++ Fundamentals Quiz

Choose the correct answer for each question.

---

### 1. What happens if you try to multiply $10^5 \times 10^5$ and store the result in a standard `int` variable?
A. It calculates $10^{10}$ perfectly.  
B. It causes an Integer Overflow because an `int` can only hold up to roughly $2 \times 10^9$.  
C. It throws a Compilation Error before the program runs.  
D. It automatically upgrades the variable to a `double`.  

### 2. What is the primary purpose of adding `ios_base::sync_with_stdio(false); cin.tie(NULL);` to your `main()` function?
A. It prevents your code from crashing on Windows.  
B. It automatically sorts all inputs.  
C. It dramatically speeds up Input and Output, preventing Time Limit Exceeded (TLE) errors.  
D. It allows you to use `printf()` and `scanf()` safely.  

### 3. You are iterating through a `for` loop from 1 to 10. You want to completely skip the number 5, but continue printing 6, 7, 8, etc. Which statement should you use inside the `if(i == 5)` block?
A. `break;`  
B. `stop;`  
C. `return;`  
D. `continue;`  

### 4. You declare a global variable `int score = 100;`. Inside a function, you declare `int score = 42;` and then print `score`. What happens?
A. It prints `100` because global variables take priority.  
B. The code crashes because you cannot use the same variable name twice.  
C. It prints `42` because the local variable "shadows" (temporarily hides) the global variable.  
D. It prints `142` as the two variables are merged.  

### 5. You have just created an empty vector: `vector<int> v;`. What happens if you immediately try to assign `v[0] = 5;`?
A. The vector automatically grows to size 1 and stores `5`.  
B. It causes a Segmentation Fault (crash) because index 0 does not exist yet.  
C. It gets pushed to the back of the vector safely.  
D. A compilation error occurs because vectors do not support square brackets.  

### 6. Which of the following is the correct C++11 "Range-Based For Loop" syntax to print every element in `vector<int> v;`?
A. `for (int x in v) { cout << x; }`  
B. `for (x of v) { cout << x; }`  
C. `for (int x : v) { cout << x; }`  
D. `foreach (int x : v) { cout << x; }`  

### 7. When writing a Custom Comparator for the `sort()` function, what MUST you return if the two elements being compared are exactly equal according to your rule?
A. `true`  
B. `false`  
C. `0`  
D. `-1`  

### 8. You want to sort a vector of emails by date. However, if two emails arrive on the exact same date, you want them to remain in the exact order they were originally listed in. Which function should you use?
A. `sort(v.begin(), v.end())`  
B. `ordered_sort(v.begin(), v.end())`  
C. `stable_sort(v.begin(), v.end())`  
D. `safe_sort(v.begin(), v.end())`  

### 9. Why is it an industry standard to use a `const vector<int>& v` when passing a large vector to a "read-only" function?
A. It prevents C++ from making a massive, slow photocopy of the vector, while guaranteeing the function cannot accidentally modify the original data.  
B. It tells the compiler to automatically sort the vector.  
C. It converts the vector into a static array for faster reading.  
D. It prevents the vector from being printed to the terminal.  

### 10. What is the #1 most common consequence of trying to dereference a `nullptr` or an invalid pointer?
A. The program safely ignores it and moves on.  
B. A Compilation Error preventing the code from building.  
C. A Memory Leak.  
D. A terrifying Segmentation Fault (Segfault) crash.  

---

## Answer Key

1. **B** (Integer Overflow occurs because `int` maxes out around $2 \times 10^9$)  
2. **C** (Fast I/O is critical for avoiding TLE in competitive programming)  
3. **D** (`continue` skips the current iteration, whereas `break` kills the entire loop)  
4. **C** (This is known as "Shadowing")  
5. **B** (You must use `v.push_back(5);` when adding elements to an empty vector)  
6. **C** (`for (int x : v)` is the correct range-based syntax)  
7. **B** (Returning `true` for equal elements violates strict weak ordering and causes runtime crashes)  
8. **C** (`stable_sort` maintains the relative order of equal elements)  
9. **A** (Pass-by-reference avoids slow copies, and `const` ensures safety)  
10. **D** (Dereferencing an invalid memory address instantly causes a Segfault)
