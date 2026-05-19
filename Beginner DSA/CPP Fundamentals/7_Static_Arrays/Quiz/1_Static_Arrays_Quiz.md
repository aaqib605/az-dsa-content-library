---
title: "Static Arrays Quiz"
slug: "static-arrays-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on array initialization, zero-indexing, and out-of-bounds errors!"
---

# Static Arrays Quiz

Test your understanding of C++'s foundational data structure: the Static Array.

---

### 1. In C++, if you declare an array of size 5 (`int arr[5];`), what is the index of the very first element?
A. 1  
B. 0  
C. -1  
D. 5  

### 2. For that same array (`int arr[5];`), what is the index of the VERY LAST element?
A. 5  
B. 6  
C. 4  
D. 0  

### 3. What is the single biggest limitation of a Static Array?
A. They can only hold integers.  
B. They are extremely slow.  
C. Their size is **fixed** at compile time and can never grow or shrink.  
D. You cannot loop through them.  

### 4. What happens if you declare an array like this: `int arr[10] = {0};`?
A. It throws an error because there is only one number.  
B. The first element becomes 0, and the rest become random garbage values.  
C. Every single element in the array is initialized to 0.  
D. The array size becomes 0.  

### 5. What happens if you declare an array like this: `int arr[10] = {1};`?
A. Every single element becomes 1.  
B. The first element becomes 1, and the remaining 9 elements become 0.  
C. It throws a syntax error.  
D. The first element becomes 1, and the rest become garbage values.  

### 6. You have `int arr[5] = {10, 20, 30, 40, 50};`. What happens if you try to `cout << arr[10];`?
A. It prints `0`.  
B. It safely stops the program with an "Array Out of Bounds" error.  
C. It accesses unallocated memory, returning unpredictable "garbage values" or potentially causing a Segmentation Fault.  
D. It wraps around and prints `10`.  

### 7. Which of the following is the proper way to pass a 1D static array to a function?
A. `void process(int arr[])`  
B. `void process(int arr[10])`  
C. `void process(int* arr)`  
D. All of the above  

### 8. True or False: When you pass a static array to a function, it is passed by value (a photocopy is made).
A. True, modifying it inside the function does not affect the original array.  
B. False, arrays naturally decay into pointers, meaning the function modifies the original array directly.  
C. True, but only if the array is small.  
D. False, it causes a compilation error.  

### 9. If you want to create an array with a size determined by a variable `N` that is input by the user (`cin >> N;`), is `int arr[N];` considered standard C++?
A. Yes, it is fully supported by the C++ Standard.  
B. No, this is a Variable Length Array (VLA) and is actually a GCC compiler extension, not standard C++.  
C. Yes, but only for `long long` arrays.  
D. No, it will always fail to compile.  

### 10. How do you find the number of elements in a static array `int arr[10];` using the `sizeof()` operator?
A. `sizeof(arr)`  
B. `sizeof(arr) / sizeof(arr[0])`  
C. `arr.length()`  
D. `arr.size()`  

---

## Answer Key

1. **B** (Arrays in C++ are 0-indexed).
2. **C** (The valid indices are 0, 1, 2, 3, 4. Attempting to access index 5 is out-of-bounds!).
3. **C** (Static arrays have a rigid, unchangeable size. This is why we use `vector` when sizes are unknown).
4. **C** (`{0}` is a special shorthand in C++ that neatly zeroes out the entire array).
5. **B** (This is a huge beginner trap! `{1}` only sets the first item to 1. The compiler sees incomplete initialization and fills the rest with 0s. It does NOT set everything to 1).
6. **C** (C++ does NOT protect you from out-of-bounds reading. It will blindly read whatever random data is sitting in that RAM slot, which is incredibly dangerous).
7. **D** (All of these are valid ways to accept an array parameter, though `int arr[]` is the most common).
8. **B** (Unlike standard variables, arrays are passed by reference implicitly. Be careful!).
9. **B** (VLAs are technically not standard C++, which is why you should use `vector` if the size is determined at runtime!).
10. **B** (`sizeof(arr)` gives the total bytes (40), so dividing by `sizeof(arr[0])` (4) gives the count (10)).
