<VIDEO_WIDGET>

<VIDEO_ID>3444</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Introduction to Vector

In the previous modules, we learned about **Static Arrays**. They are incredibly fast and efficient, but they have one massive flaw: **their size is fixed**.

If you create an array `int arr[10];`, it can _never_ hold 11 items. But what if you are reading data from a user and you don't know how many numbers they will enter until the program is already running?

Enter **`vector`**: The Dynamic Array.

---

## 1. Why `vector` Exists

A `vector` is a "smart" array that can **grow and shrink automatically** as needed.

- You don't need to know the size in advance.
- You can keep adding elements to it, and it will magically allocate more memory behind the scenes.
- In Competitive Programming, vectors are the absolute standard. You will use them in almost every problem!

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/5737941d-e3e8-4b0b-8e20-957a2975b4a5.png" alt="Vector Vs Array" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## 2. Declaration

To use a vector, you technically need `#include <vector>`, but our magic spell `#include <bits/stdc++.h>` already includes it for us!

The syntax requires you to specify the **data type** inside angle brackets `< >`.

```cpp
// Creates an empty vector of integers
vector<int> v;

// Creates an empty vector of strings
vector<string> names;

// Creates a vector of size 5, with all elements initialized to 0
vector<int> v2(5, 0);

// Initializer List: Creates a vector with hardcoded values
vector<int> primes = {2, 3, 5, 7};
```

---

## 3. The Magic Function: `push_back()`

How do you add something to a vector if it starts empty? You use the `.push_back()` function. This adds a new element to the **back** (end) of the vector, increasing its size by 1.

```cpp
vector<int> v; // Size is 0

v.push_back(10); // v now contains: [10]
v.push_back(20); // v now contains: [10, 20]
v.push_back(30); // v now contains: [10, 20, 30]
```

> 💡 **Interview Insight:** Why are vectors the absolute standard in CP and system-level engineering? Because `.push_back()` operates in **amortized $O(1)$ time**. This means adding an element to the back is incredibly fast, practically identical to placing an item in a static array!

---

## 4. Size and Indexing

### `.size()`

To find out how many elements are currently inside your vector, use the `.size()` function.

### Indexing (`[ ]`)

Just like static arrays, vectors are **0-indexed**. You can access or modify elements using square brackets `[ ]`.

```cpp
vector<int> v;
v.push_back(10);
v.push_back(20);
v.push_back(30);

cout << "Size of vector: " << v.size() << "\n"; // Output: 3

cout << "First element: " << v[0] << "\n"; // Output: 10
cout << "Last element: " << v[2] << "\n";  // Output: 30

// Modifying an element
v[1] = 99; // The vector is now [10, 99, 30]
```

> ⚠️ **Warning:** You cannot use `v[i]` to _add_ a new element if that index doesn't exist yet! If `v` is empty, doing `v[0] = 5;` will cause a Segmentation Fault (Crash). You **must** use `push_back()` to add new elements!

### Other Essential Vector Methods

While `.push_back()` and `.size()` are the bread and butter, here are three more methods you will constantly need:

- **`.pop_back()`**: Removes the very last element of the vector. (Also operates in $O(1)$ time!)
- **`.empty()`**: Returns `true` if the vector has zero elements, and `false` otherwise. (Much cleaner and safer than checking `v.size() == 0`).
- **`.clear()`**: Wipes the vector completely clean, dropping its size back to 0. Extremely useful when resetting a vector inside a `while(t--)` test case loop!

```cpp
vector<int> v = {10, 20, 30};

v.pop_back(); // Removes 30. Vector is now [10, 20]

if (!v.empty()) {
    cout << "Vector is not empty!\n";
}

v.clear(); // Vector is now completely empty!
```

---

## 5. Input and Output (Basic Traversal)

There are two common ways to take input for a vector.

### Method A: Pushing elements one by one

If you create an empty vector, you must read the value into a temporary variable, then push it.

```cpp
int n;
cin >> n;

vector<int> v;
for (int i = 0; i < n; i++) {
    int temp;
    cin >> temp;
    v.push_back(temp); // Grow the vector!
}
```

### Method B: Pre-allocating size (Faster)

If you know the size `n` immediately, it is better to create a vector of size `n` and use `cin` directly with indexing.

```cpp
int n;
cin >> n;

// Create a vector of size n
vector<int> v(n);

// Now we can safely use indexing!
for (int i = 0; i < n; i++) {
    cin >> v[i];
}
```

### Printing the Vector

Remember the **Range-Based For Loop** we sneaked into the Loops module? It was practically built for vectors!

```cpp
cout << "The vector elements are: ";

// Reads: "For every integer 'x' inside the vector 'v'"
for (int x : v) {
    cout << x << " ";
}
cout << "\n";
```

_(You can also use a standard `for (int i = 0; i < v.size(); i++)` loop if you need the index `i` for your logic!)_

</READING_WIDGET>
