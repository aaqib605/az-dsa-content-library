---
title: "2D Arrays and Matrices Quiz"
slug: "2d-arrays-and-matrices-quiz"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
duration: ""
updatedAt: "2026-05-19"
description: "Test your knowledge on grids, row-major order, nested loops, and multidimensional arrays."
---

# 2D Arrays and Matrices Quiz

Test your understanding of mapping grids and handling multidimensional data!

---

### 1. In a standard 2D Array `int arr[3][4];`, what does the `3` represent?
A. The number of Columns.  
B. The number of Rows.  
C. The depth of the array.  
D. The total number of elements.  

### 2. If you want to access the very bottom-right element in a `3 x 4` matrix, what indices do you use?
A. `arr[3][4]`  
B. `arr[4][3]`  
C. `arr[2][3]`  
D. `arr[-1][-1]`  

### 3. C++ stores 2D arrays in contiguous memory, placing items row-by-row. What is this concept called?
A. Column-Major Order  
B. Row-Major Order  
C. Grid-Lock Memory  
D. Matrix Memory Allocation  

### 4. Because of the memory layout discussed in Question 3, which traversal method is significantly faster and more "cache-friendly"?
A. Column-wise Traversal  
B. Row-wise Traversal  
C. Diagonal Traversal  
D. Random Traversal  

### 5. In a square matrix of size $N \times N$, what is always true for any element lying exactly on the **Main Diagonal** (top-left to bottom-right)?
A. Its row index is 0.  
B. Its row index equals its column index (`i == j`).  
C. The sum of its row and column indices is $N - 1$.  
D. Its value is 1.  

### 6. You want to pass a raw static 2D array to a function: `void print(int arr[][])`. What happens?
A. It prints the matrix perfectly.  
B. It causes a runtime error.  
C. It causes a Compilation Error because you MUST specify the column size in the parameter.  
D. It only prints the first row.  

### 7. Because passing raw 2D arrays to functions is annoying, what do modern competitive programmers almost exclusively use instead?
A. Pointers  
B. `vector<vector<int>>`  
C. 1D Arrays mapped with math  
D. `matrix<int>`  

### 8. What is the correct syntax to find the number of rows in a `vector<vector<int>> grid`?
A. `grid.rows()`  
B. `grid.size()`  
C. `grid[0].size()`  
D. `grid.length()`  

### 9. What is the correct syntax to find the number of columns in the first row of a `vector<vector<int>> grid`?
A. `grid.cols()`  
B. `grid.size()`  
C. `grid[0].size()`  
D. `grid.length()`  

### 10. You want to iterate over the **Secondary Diagonal** (top-right to bottom-left) of an $N \times N$ matrix. Which loop setup is correct?
A. `for (int i = 0; i < N; i++) { cout << arr[i][i]; }`  
B. `for (int i = 0; i < N; i++) { cout << arr[i][N - 1 - i]; }`  
C. `for (int i = N - 1; i >= 0; i--) { cout << arr[i][i]; }`  
D. `for (int i = 0; i < N; i++) { cout << arr[N][i]; }`  

---

## Answer Key

1. **B** (The first bracket always defines the Rows, the second defines the Columns).
2. **C** (Because of 0-indexing, a 3x4 matrix has rows `0,1,2` and columns `0,1,2,3`. The bottom right is `2, 3`).
3. **B** (Row-Major Order means `arr[0][0]` sits right next to `arr[0][1]` in RAM).
4. **B** (Traversing row-wise means the CPU can fetch entire chunks of contiguous memory into the cache at once).
5. **B** (The main diagonal coordinates are `(0,0)`, `(1,1)`, `(2,2)`, etc., meaning `i == j`).
6. **C** (The compiler needs the column size to calculate memory offsets. Because of Row-Major order, the physical address is calculated as: `Base Address + (i * Total Columns + j) * sizeof(type)`. Without knowing `Total Columns`, the math is impossible!).
7. **B** (Vectors of Vectors are dynamically resizable and can be easily passed by reference!).
8. **B** (Since it is a vector of vectors, `grid.size()` tells you how many inner vectors (rows) exist).
9. **C** (`grid[0]` gives you the first row (a vector), so calling `.size()` on it gives the number of columns! **Pro Tip:** Always check `if (!grid.empty())` before calling `grid[0]` to avoid a Segmentation Fault on empty matrix inputs).
10. **B** (The secondary diagonal coordinates always satisfy `i + j = N - 1`, which means `j = N - 1 - i`).
