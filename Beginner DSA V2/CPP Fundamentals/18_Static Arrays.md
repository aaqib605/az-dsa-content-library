<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Static Arrays

So far, we have been using variables to store a single piece of data. If you want to store the age of a student, you create an `int age`. 
But what if you are a teacher and need to store the ages of **100 students**? 

You *could* create 100 variables (`age1`, `age2`, `age3`...), but that would be a nightmare to manage. 

The solution? **Arrays**.

---

## 1. What is an Array?

An array is a data structure that can store a fixed-size, sequential collection of elements of the **same data type**.
Think of an array like a row of lockers in a hallway. They are all right next to each other, they are all the same size, and each one has a specific number.

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/7e11185b-0e10-4a05-990d-e0e9afd6781c.png" alt="Array Lockers" style="max-width: 100%; height: auto;" identifier="az-img-upload">

### Declaration and Initialization

To declare an array in C++, you specify the type of data it holds, its name, and its **fixed size**.

```cpp
// Creates an array of 5 integers (currently filled with garbage values)
int scores[5]; 

// Creates an array of 5 integers and initializes them
int ages[5] = {18, 19, 20, 21, 22}; 

// You can omit the size if you provide the elements immediately
int primes[] = {2, 3, 5, 7, 11}; 

// Initializes the first element to 0, and automatically sets the rest to 0
int zeroes[100] = {0}; 
```

> 💡 **Pro Tip:** As noted above, an array declared inside `main()` (locally) without initialization will contain random garbage values. However, in competitive programming, it is a very common practice to declare large arrays *outside* of `main()` (globally). Global arrays are automatically initialized with zeros!

---

## 2. Zero-Based Indexing

How do we access a specific locker? We use an **Index**. 
In C++ (and most programming languages), **arrays start counting from 0, not 1!**

- The first element is at index `0`.
- The last element of an array of size `N` is at index `N - 1`.

```cpp
int arr[5] = {10, 20, 30, 40, 50};

cout << arr[0] << "\n"; // Prints 10 (First element)
cout << arr[4] << "\n"; // Prints 50 (Last element)

// WARNING: arr[5] is OUT OF BOUNDS! This will cause garbage data or a crash.
```

---

## 3. Input, Output, and Traversing

Because arrays use sequential numbers (0, 1, 2, 3...), they are perfectly paired with **loops**.

### Taking Input into an Array
```cpp
int N;
cin >> N;
int arr[N]; // Create an array of size N

// Read N elements from the user
for (int i = 0; i < N; i++) {
    cin >> arr[i];
}
```

### Printing an Array
```cpp
// Print all N elements
for (int i = 0; i < N; i++) {
    cout << arr[i] << " ";
}
cout << "\n";
```

### The Range-Based `for` Loop (Revisited)
Remember the sneak peek from the Loops section? If you just need to *read* or *print* every element in an array and don't care about the exact index, you can use the super-clean range-based loop:

```cpp
int arr[4] = {5, 10, 15, 20};

for (int val : arr) {
    cout << val << " ";
}
```

---

## 4. Common Array Operations

In competitive programming, you will perform these basic operations on arrays constantly.

### Updating Values
You can modify an element exactly like a normal variable.
```cpp
int arr[3] = {1, 2, 3};
arr[1] = 99; // Changes the second element (index 1) to 99
```

### Finding Sum, Max, and Min
To find aggregate data, you iterate through the array and keep a running tracker.

```cpp
int arr[5] = {10, 5, 20, 8, 15};

// Note: The sum of many integers easily overflows the 32-bit limit! Always use long long.
long long sum = 0; 
int max_val = arr[0]; // Start by assuming the first element is the max
int min_val = arr[0]; // Start by assuming the first element is the min

for (int i = 0; i < 5; i++) {
    sum += arr[i];
    
    if (arr[i] > max_val) {
        max_val = arr[i];
    }
    
    if (arr[i] < min_val) {
        min_val = arr[i];
    }
}

cout << "Sum: " << sum << ", Max: " << max_val << ", Min: " << min_val << "\n";
```

### Counting Elements Satisfying a Condition
Want to know how many even numbers are in the array? Set up a counter!

```cpp
int arr[6] = {1, 2, 3, 4, 5, 6};
int even_count = 0;

for (int i = 0; i < 6; i++) {
    if (arr[i] % 2 == 0) {
        even_count++;
    }
}

cout << "There are " << even_count << " even numbers.\n";
```

</READING_WIDGET>
