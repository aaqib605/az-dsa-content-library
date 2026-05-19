---
title: "Input, Output, and Online Judge Quiz"
slug: "input-output-and-online-judge-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on cin, cout, fast I/O, and handling Online Judge environments."
---

# Input, Output, and Online Judge Quiz

Test your understanding of how to communicate with users and Online Judges!

---

### 1. Which operator is used with `cin` to take input?
A. `<<` (Insertion Operator)  
B. `>>` (Extraction Operator)  
C. `||`  
D. `::`  

### 2. If the user types `10 20` separated by a space, how do you read both numbers into variables `a` and `b`?
A. `cin >> a, b;`  
B. `cin >> a >> b;`  
C. `cin(a, b);`  
D. `input >> a >> " " >> b;`  

### 3. Why is using `\n` preferred over `endl` in competitive programming?
A. `endl` causes memory leaks.  
B. `\n` looks cleaner in the code.  
C. `endl` flushes the output buffer every single time, which is extremely slow and can cause Time Limit Exceeded (TLE).  
D. `\n` works on both Windows and Mac, while `endl` only works on Linux.  

### 4. What is the magic incantation added at the start of `main()` to massively speed up Input/Output operations?
A. `#pragma GCC optimize("O3")`  
B. `ios_base::fast_io();`  
C. `ios_base::sync_with_stdio(false); cin.tie(NULL);`  
D. `cin.speed(MAX);`  

### 5. If you want to print a `double` variable exactly up to 5 decimal places, which library must you include to use `setprecision()`?
A. `<iostream>`  
B. `<math.h>`  
C. `<iomanip>`  
D. `<precision>`  

### 6. An Online Judge gives you a "Wrong Answer (WA)" verdict. What does this mean?
A. Your program crashed.  
B. Your program ran out of time.  
C. Your program compiled and ran, but the output did not exactly match the expected output.  
D. You forgot to include a specific library.  

### 7. If you need to print a massive 2D matrix of 100,000 numbers, which combination of fast I/O practices is the absolute most efficient?
A. `cin >> matrix[i][j]`  
B. `cout` and `endl`  
C. `cin.tie(NULL)` with `cout` and `\n`  
D. `cout` and `flush`  

### 8. What does `ios_base::sync_with_stdio(false);` actually do under the hood?
A. It disables multi-threading.  
B. It unsynchronizes C++ streams (`cin`/`cout`) from C streams (`scanf`/`printf`), skipping the safety checks and boosting speed.  
C. It forces the output buffer to flush instantly.  
D. It prevents the program from crashing if the user types a string instead of an int.  

### 9. What is a "Hidden Test Case" on an Online Judge?
A. A test case that crashes the judge's servers.  
B. A test case that tests your code against completely unseen inputs to verify it isn't just hardcoded to pass the examples.  
C. A test case that doesn't count towards your final score.  
D. A test case written in a different programming language.  

### 10. If an Online Judge gives you a "Time Limit Exceeded (TLE)" verdict, what is the most likely culprit?
A. You forgot a semicolon.  
B. Your program printed the wrong answer.  
C. Your algorithm has an inefficient Time Complexity (e.g., $O(N^2)$ when $O(N)$ was expected) or you have an infinite loop.  
D. You tried to read an array out of bounds.  

---

## Answer Key

1. **B** (`cin >>` extracts data from the input stream).
2. **B** (`cin >> a >> b;` chains the extraction operators seamlessly).
3. **C** (Flushing the buffer with `endl` forces the computer to write to the console immediately, which is incredibly slow inside large loops).
4. **C** (This lines up two optimizations: `sync_with_stdio(false)` un-syncs C and C++ streams so they don't block each other, and `cin.tie(NULL)` unties `cin` from `cout` so the output buffer isn't flushed every time you ask for input).
5. **C** (`<iomanip>` stands for Input/Output Manipulators and contains `setprecision`).
6. **C** (WA means the logic is flawed or the output formatting is slightly incorrect).
7. **C** (Combining the fast I/O boilerplate with `\n` instead of `endl` guarantees that a massive data dump like a 100,000-element matrix won't bottleneck your program's execution time).
8. **B** (By default, C++ keeps its streams synced with standard C streams so you can mix `cout` and `printf`. Disabling this sync removes the bottleneck).
9. **B** (Hidden test cases are the true test of your logic's robustness).
10. **C** (TLE means your logic took too long to run. You must optimize your approach!).
