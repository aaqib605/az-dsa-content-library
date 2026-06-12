<READING_WIDGET>
# Static Arrays Quiz

Test your understanding of C++'s foundational data structure: the Static Array.

</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In C++, if you declare an array of size 5 (`int arr[5];`), what is the index of the very first element?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Arrays in C++ are 0-indexed
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                1
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                0
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                -1
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                5
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **For that same array (`int arr[5];`), what is the index of the VERY LAST element?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The valid indices are 0, 1, 2, 3, 4. Attempting to access index 5 is out-of-bounds!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                5
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                6
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                4
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                0
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the single biggest limitation of a Static Array?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Static arrays have a rigid, unchangeable size. This is why we use `vector` when sizes are unknown
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                They can only hold integers.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                They are extremely slow.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Their size is **fixed** at compile time and can never grow or shrink.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                You cannot loop through them.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What happens if you declare an array like this: `int arr[10] = {0};`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `{0}` is a special shorthand in C++ that neatly zeroes out the entire array
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It throws an error because there is only one number.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The first element becomes 0, and the rest become random garbage values.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Every single element in the array is initialized to 0.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The array size becomes 0.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What happens if you declare an array like this: `int arr[10] = {1};`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        This is a huge beginner trap! `{1}` only sets the first item to 1. The compiler sees incomplete initialization and fills the rest with 0s. It does NOT set everything to 1
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Every single element becomes 1.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The first element becomes 1, and the remaining 9 elements become 0.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It throws a syntax error.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The first element becomes 1, and the rest become garbage values.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **You have `int arr[5] = {10, 20, 30, 40, 50};`. What happens if you try to `cout << arr[10];`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        C++ does NOT protect you from out-of-bounds reading. It will blindly read whatever random data is sitting in that RAM slot, which is incredibly dangerous
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It prints `0`.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It safely stops the program with an "Array Out of Bounds" error.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It accesses unallocated memory, returning unpredictable "garbage values" or potentially causing a Segmentation Fault.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It wraps around and prints `10`.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which of the following is the proper way to pass a 1D static array to a function?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        All of these are valid ways to accept an array parameter, though `int arr[]` is the most common
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `void process(int arr[])`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `void process(int arr[10])`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `void process(int* arr)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                All of the above
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **True or False: When you pass a static array to a function, it is passed by value (a photocopy is made).**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Unlike standard variables, arrays are passed by reference implicitly. Be careful!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                True, modifying it inside the function does not affect the original array.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                False, arrays naturally decay into pointers, meaning the function modifies the original array directly.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                True, but only if the array is small.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                False, it causes a compilation error.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you want to create an array with a size determined by a variable `N` that is input by the user (`cin >> N;`), is `int arr[N];` considered standard C++?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        VLAs are technically not standard C++, which is why you should use `vector` if the size is determined at runtime!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Yes, it is fully supported by the C++ Standard.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                No, this is a Variable Length Array (VLA) and is actually a GCC compiler extension, not standard C++.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Yes, but only for `long long` arrays.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                No, it will always fail to compile.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **How do you find the number of elements in a static array `int arr[10];` using the `sizeof()` operator?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `sizeof(arr)` gives the total bytes (40), so dividing by `sizeof(arr[0])` (4) gives the count (10
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `sizeof(arr)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `sizeof(arr) / sizeof(arr[0])`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `arr.length()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `arr.size()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Static Arrays, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>
