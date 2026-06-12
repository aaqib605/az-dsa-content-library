<READING_WIDGET>
# 2D Arrays and Matrices Quiz

Test your understanding of mapping grids and handling multidimensional data!
</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In a standard 2D Array `int arr[3][4];`, what does the `3` represent?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The first bracket always defines the Rows, the second defines the Columns
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number of Columns.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number of Rows.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The depth of the array.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The total number of elements.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you want to access the very bottom-right element in a `3 x 4` matrix, what indices do you use?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Because of 0-indexing, a 3x4 matrix has rows `0,1,2` and columns `0,1,2,3`. The bottom right is `2, 3`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `arr[3][4]`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `arr[4][3]`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `arr[2][3]`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `arr[-1][-1]`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **C++ stores 2D arrays in contiguous memory, placing items row-by-row. What is this concept called?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Row-Major Order means `arr[0][0]` sits right next to `arr[0][1]` in RAM
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Column-Major Order
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Row-Major Order
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Grid-Lock Memory
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Matrix Memory Allocation
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Because of the memory layout discussed in Question 3, which traversal method is significantly faster and more "cache-friendly"?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Traversing row-wise means the CPU can fetch entire chunks of contiguous memory into the cache at once
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Column-wise Traversal
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Row-wise Traversal
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Diagonal Traversal
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Random Traversal
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In a square matrix of size $N \times N$, what is always true for any element lying exactly on the **Main Diagonal** (top-left to bottom-right)?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The main diagonal coordinates are `(0,0)`, `(1,1)`, `(2,2)`, etc., meaning `i == j`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Its row index is 0.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Its row index equals its column index (`i == j`).
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The sum of its row and column indices is $N - 1$.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Its value is 1.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **You want to pass a raw static 2D array to a function: `void print(int arr[][])`. What happens?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The compiler needs the column size to calculate memory offsets. Because of Row-Major order, the physical address is calculated as: `Base Address + (i * Total Columns + j) * sizeof(type)`. Without knowing `Total Columns`, the math is impossible!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It prints the matrix perfectly.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It causes a runtime error.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It causes a Compilation Error because you MUST specify the column size in the parameter.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It only prints the first row.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Because passing raw 2D arrays to functions is annoying, what do modern competitive programmers almost exclusively use instead?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Vectors of Vectors are dynamically resizable and can be easily passed by reference!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Pointers
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `vector<vector<int>>`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                1D Arrays mapped with math
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `matrix<int>`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the correct syntax to find the number of rows in a `vector<vector<int>> grid`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Since it is a vector of vectors, `grid.size()` tells you how many inner vectors (rows) exist
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid.rows()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid.size()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid[0].size()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid.length()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the correct syntax to find the number of columns in the first row of a `vector<vector<int>> grid`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `grid[0]` gives you the first row (a vector), so calling `.size()` on it gives the number of columns! **Pro Tip:** Always check `if (!grid.empty())` before calling `grid[0]` to avoid a Segmentation Fault on empty matrix inputs
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid.cols()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid.size()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid[0].size()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `grid.length()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **You want to iterate over the **Secondary Diagonal** (top-right to bottom-left) of an $N \times N$ matrix. Which loop setup is correct?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The secondary diagonal coordinates always satisfy `i + j = N - 1`, which means `j = N - 1 - i`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `for (int i = 0; i < N; i++) { cout << arr[i][i]; }`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `for (int i = 0; i < N; i++) { cout << arr[i][N - 1 - i]; }`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `for (int i = N - 1; i >= 0; i--) { cout << arr[i][i]; }`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `for (int i = 0; i < N; i++) { cout << arr[N][i]; }`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, 2D Arrays and Matrices, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>
