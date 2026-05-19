---
title: "Variables, Data Types, and Operators Quiz"
slug: "variables-data-types-and-operators-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on standard data types, integer overflow, ASCII, and the modulo operator."
---

# Variables, Data Types, and Operators Quiz

Test your understanding of how C++ stores and manipulates data!

---

### 1. Roughly what is the maximum positive value that a standard 32-bit `int` can store in C++?
A. $10^5$  
B. $10^9$ ($2 \times 10^9$)  
C. $10^{18}$  
D. Infinity  

### 2. If a problem states the answer can be up to $10^{15}$, which data type MUST you use to avoid Integer Overflow?
A. `int`  
B. `double`  
C. `long long`  
D. `float`  

### 3. What is the value of `7 / 2` in standard C++?
A. `3.5`  
B. `4`  
C. `3`  
D. A compilation error  

### 4. What does the Modulo Operator `%` calculate?
A. The percentage.  
B. The quotient of division.  
C. The remainder of division.  
D. The absolute value.  

### 5. What is the result of `15 % 4`?
A. `3.75`  
B. `3`  
C. `4`  
D. `1`  

### 6. You want to cast a `double` variable named `price` into an integer using standard C++ practices. Which syntax is preferred?
A. `integer(price)`  
B. `(int)price` (or `static_cast<int>(price)`)  
C. `int: price`  
D. `convert.to_int(price)`  

### 7. What is the ASCII value of the character `'A'`?
A. 0  
B. 65  
C. 97  
D. 48  

### 8. `a++` is known as the post-increment operator. If `int a = 5; int b = a++;`, what are the values of `a` and `b`?
A. `a = 6`, `b = 6`  
B. `a = 6`, `b = 5`  
C. `a = 5`, `b = 6`  
D. `a = 5`, `b = 5`  

### 9. You need to store the exact value of Pi ($3.1415926535...$) with high precision. Which data type should you prefer?
A. `float`  
B. `int`  
C. `double`  
D. `long long`  

### 10. What happens if you add two `int` variables that are both equal to $2 \times 10^9$?
A. They successfully store $4 \times 10^9$.  
B. They cause an Integer Overflow, wrapping around to a massive negative number.  
C. The program refuses to compile.  
D. C++ automatically converts them into a `long long`.  

---

## Answer Key

1. **B** (An `int` caps out at roughly $2.14 \times 10^9$. Always remember this limit!).
2. **C** (`long long` uses 64 bits and can store numbers up to roughly $9 \times 10^{18}$).
3. **C** (Integer division truncates the decimal part completely. `3.5` becomes `3`).
4. **C** (Modulo `%` gives you the remainder, which is critical for finding odd/even numbers or wrapping around limits).
5. **B** ($15 / 4 = 3$ with a remainder of $3$).
6. **B** (Both the traditional C-style cast `(int)price` and the modern, safer C++ `static_cast<int>(price)` explicitly truncate the decimal part and convert the value to an integer).
7. **B** (`'A'` is 65, `'a'` is 97, and `'0'` is 48. Knowing these is a massive hack for string problems!).
8. **B** (Because it is post-increment, `b` gets the *current* value of `a` (5), and *then* `a` increments to 6).
9. **C** (`double` provides double the precision of a standard `float` and is the industry standard for floating-point math).
10. **B** (Adding these values exceeds the maximum limit of a signed 32-bit integer. In practice, this causes it to wrap around to a negative number due to binary representation limits. In standard C++, this is known as **Undefined Behavior**, meaning the compiler can break your logic completely. Always scale up to `long long`!).
