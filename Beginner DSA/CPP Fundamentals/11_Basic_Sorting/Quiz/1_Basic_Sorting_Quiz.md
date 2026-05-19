---
title: "Basic Sorting Quiz"
slug: "basic-sorting-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on the sort() function, custom comparators, and stable sorting."
---

# Basic Sorting Quiz

Test your understanding of the most heavily used C++ algorithm function!

---

### 1. What is the correct syntax to sort an entire `vector<int> v` in **ascending order**?
A. `v.sort();`  
B. `sort(v);`  
C. `sort(v.begin(), v.end());`  
D. `sort(v.front(), v.back());`  

### 2. Under the hood, the C++ `sort()` function uses "IntroSort". What time complexity does this guarantee even in the worst-case scenario?
A. $O(N^2)$  
B. $O(N)$  
C. $O(\log N)$  
D. $O(N \log N)$  

### 3. How can you easily sort a vector in **descending order** (largest to smallest) using iterators?
A. `sort(v.end(), v.begin());`  
B. `sort(v.rbegin(), v.rend());`  
C. `sort_desc(v.begin(), v.end());`  
D. `reverse_sort(v.begin(), v.end());`  

### 4. You are sorting a `vector<pair<int, int>> v;`. By default, what does `sort()` do if the first elements of two pairs are exactly equal?
A. It crashes.  
B. It ignores them and leaves them unsorted.  
C. It gracefully falls back and sorts them based on their second elements.  
D. It adds the two elements together.  

### 5. You are writing a Custom Comparator function. What MUST your function return if the two elements being compared are considered exactly equal according to your rule?
A. `true`  
B. `false`  
C. `0`  
D. `-1`  

### 6. You sort a list of emails by date. Later, you sort the same list by sender. You notice that emails from the same sender are no longer ordered by date. Which function should you use to guarantee that equal elements keep their original relative order?
A. `secure_sort()`  
B. `safe_sort()`  
C. `stable_sort()`  
D. `ordered_sort()`  

### 7. What is the modern C++ syntax feature that allows you to write a custom comparator function *inline* directly inside the `sort()` call?
A. Lambda Functions  
B. Inline Macros  
C. Pointers  
D. Templates  

### 8. Which standard C++ library MUST be included to use the `sort()` function?
A. `<iostream>`  
B. `<vector>`  
C. `<algorithm>`  
D. `<math>`  

### 9. If you want to sort an array of $N$ elements (`int arr[N];`), what is the correct syntax?
A. `sort(arr.begin(), arr.end());`  
B. `sort(arr, arr + N);`  
C. `sort(&arr[0], &arr[N-1]);`  
D. `arr.sort();`  

### 10. When sorting a `vector<string>`, how does C++ determine the order by default?
A. By the length of the string.  
B. By the ASCII values of the characters (Lexicographical / Dictionary order).  
C. Alphabetically, ignoring case.  
D. Randomly.  

---

## Answer Key

1. **C** (`sort()` requires a starting iterator and an ending iterator).
2. **D** (IntroSort is a hybrid that guarantees fast $O(N \log N)$ sorting, making it much safer than a naive QuickSort).
3. **B** (`rbegin()` and `rend()` stand for "reverse begin" and "reverse end").
4. **C** (This automatic fallback behavior makes sorting pairs incredibly powerful in competitive programming).
5. **B** (Returning `true` for equal elements violates the "Strict Weak Ordering" rule and will cause a runtime crash!).
6. **C** (`stable_sort` does exactly this, which is critical when doing multi-layered sorting in Software Engineering).
7. **A** (Lambda functions `[](int a, int b) { return a < b; }` keep your code incredibly clean and localized).
8. **C** (The `<algorithm>` header contains almost all of the powerful data manipulation functions in C++).
9. **B** (`arr` acts as a pointer to the first element, and `arr + N` acts as a pointer to the memory address just past the last element. **Note:** Option C is a dangerous bug! The `sort` function requires an *exclusive* upper bound. Using `&arr[N-1]` stops sorting one element too early, completely missing the last item in the array).
10. **B** (Strings are compared character by character using their ASCII values, meaning `"Apple"` comes before `"apple"` because uppercase letters have lower ASCII values).
