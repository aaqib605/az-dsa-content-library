---
title: "Introduction to Vector Quiz"
slug: "introduction-to-vector-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on dynamic arrays, push_back, and vector capacity."
---

# Introduction to Vector Quiz

Test your understanding of C++ Vectors, the ultimate dynamic array!

---

### 1. What is the fundamental advantage of a `vector` over a Static Array?
A. It can store multiple different data types at once.  
B. Its size is **dynamic**; it can grow or shrink automatically as needed.  
C. It is immune to out-of-bounds errors.  
D. It takes up absolutely zero memory until used.  

### 2. If you create an empty vector `vector<int> v;`, what happens if you try to do `v[0] = 5;`?
A. It safely pushes 5 to the back of the vector.  
B. The vector expands to size 1 automatically.  
C. It triggers Undefined Behavior (often a Segmentation Fault) because you are writing to unallocated memory.  
D. A compilation error occurs.  

### 3. What is the correct way to add an element to the end of a vector?
A. `v.add(10);`  
B. `v.insert_end(10);`  
C. `v.push_back(10);`  
D. `v[last] = 10;`  

### 4. What is the **amortized time complexity** of the `push_back()` operation?
A. $O(N)$  
B. $O(\log N)$  
C. $O(N^2)$  
D. Amortized $O(1)$  

### 5. Which vector method easily removes the very last element?
A. `v.remove_last();`  
B. `v.pop_back();`  
C. `v.delete();`  
D. `v.clear_end();`  

### 6. If you want to completely wipe a vector clean so it has a size of 0, which method should you use?
A. `v.erase();`  
B. `v.empty();`  
C. `v.clear();`  
D. `v = 0;`  

### 7. How do you initialize a vector `v` with 10 elements, all set to the number `-1`?
A. `vector<int> v(10) = -1;`  
B. `vector<int> v = {-1 * 10};`  
C. `vector<int> v(10, -1);`  
D. `vector<int> v[-1, 10];`  

### 8. What does `v.front()` and `v.back()` return?
A. Iterators to the beginning and end of the vector.  
B. References to the actual first and last elements in the vector.  
C. The indices of the first and last elements.  
D. A new vector containing those elements.  

### 9. Why is calling `v.erase(v.begin())` (removing the first element) considered a slow operation?
A. Because it deletes the entire vector.  
B. Because it forces the vector to reallocate completely new memory.  
C. Because every single remaining element must be shifted one position to the left, taking $O(N)$ time.  
D. Because the compiler has to search for the beginning.  

### 10. If you know in advance exactly how many items you are going to `push_back()` into a vector, what method can you call to pre-allocate memory and make the insertions even faster?
A. `v.reserve()`  
B. `v.resize()`  
C. `v.allocate()`  
D. `v.capacity()`  

---

## Answer Key

1. **B** (Unlike static arrays, vectors manage their own memory and resize themselves on the fly).
2. **C** (A vector starts with a size of 0. Accessing `v[0]` before allocating that space writes to memory you don't own, causing Undefined Behavior and likely a hard crash!).
3. **C** (`push_back()` is the standard method for appending elements).
4. **D** (Vectors double their internal capacity when full. Because of this clever math, adding elements is extremely fast on average).
5. **B** (`pop_back()` removes the last element and reduces the size by 1).
6. **C** (`clear()` removes all elements, which is perfect for resetting data between multiple test cases).
7. **C** (`vector<int> v(size, default_value)` is the powerful constructor syntax).
8. **B** (They give you direct access to the first and last values, unlike `.begin()` which returns an iterator).
9. **C** (Removing from the front of a dynamic array is highly inefficient. If you need to do this often, use a `deque` or `queue`!).
10. **A** (`v.reserve(100)` increases the underlying *capacity* without changing the logical size, preventing costly memory reallocations during a `push_back` loop. Do not confuse this with `v.resize()`, which actually populates the vector with 0s and changes its size!).
