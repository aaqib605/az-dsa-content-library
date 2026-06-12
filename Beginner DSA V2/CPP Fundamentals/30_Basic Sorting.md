<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Basic Sorting

If there is one algorithm you will use in almost every single competitive programming contest, it is **Sorting**. 

Imagine trying to find a specific word in a dictionary where the pages are shuffled randomly. It would be a nightmare! But because a dictionary is *sorted* alphabetically, you can find any word in seconds. 

---

## 1. Why Sorting is Useful
Sorting brings order to chaos. Once data is sorted, several complex problems become trivially easy:
- **Finding Extremes:** The minimum is instantly at index `0`, and the maximum is at the last index.
- **Grouping:** All duplicate elements sit right next to each other.
- **Fast Searching:** You can use Binary Search (which we will learn later) to find elements in $O(\log N)$ time!

---

## 2. Sorting Arrays and Vectors
C++ provides a magical built-in function called `sort()`. It operates in **$O(N \log N)$ time**, which is incredibly fast and optimal for general-purpose sorting.

*(Note: Under the hood, C++ uses **IntroSort**—a clever hybrid of QuickSort, HeapSort, and Insertion Sort. This guarantees an $O(N \log N)$ worst-case time complexity, making it safer than a naive QuickSort!)*

### Sorting a Static Array
To sort an array, you give the `sort()` function two "pointers": where to start, and where to end.
```cpp
int arr[] = {4, 1, 8, 2, 9};
int n = 5; // Size of the array

// sort(start_pointer, end_pointer)
sort(arr, arr + n);

// arr is now: {1, 2, 4, 8, 9}
```

### Sorting a Vector
For vectors, we use **iterators** (`.begin()` and `.end()`) instead of pointers.
```cpp
#include <iostream>
#include <vector>
#include <algorithm> // Required for sort()!
using namespace std;

int main() {
    vector<int> v = {4, 1, 8, 2, 9};

    // sort(start_iterator, end_iterator)
    sort(v.begin(), v.end());

    // v is now: {1, 2, 4, 8, 9}
    return 0;
}
```

> 💡 **Fun Fact:** The `sort()` function is incredibly versatile! If you pass it a `vector<string>`, it will automatically sort the strings alphabetically right out of the box!

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/c15f1025-bf4b-4759-afb6-abba387f1da5.png" alt="Sorting Machine" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## 3. Descending Order

By default, `sort()` organizes elements in **Ascending Order** (smallest to largest). What if we want the largest elements first?

There are two easy ways to do this:

**Method A: Using `greater<int>()`**
You can pass a third argument to `sort()` that tells it to reverse its logic.
```cpp
vector<int> v = {4, 1, 8, 2, 9};
sort(v.begin(), v.end(), greater<int>());
// v is now: {9, 8, 4, 2, 1}
```

**Method B: Using Reverse Iterators (Vectors only)**
Instead of `.begin()` and `.end()`, use `.rbegin()` (reverse begin) and `.rend()` (reverse end).
```cpp
vector<int> v = {4, 1, 8, 2, 9};
sort(v.rbegin(), v.rend());
// v is now: {9, 8, 4, 2, 1}
```

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/3f47c058-a8bf-4c0a-a8f9-5107be8e47a4.png" alt="Vector Iterators" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## 4. Custom Comparators (The Ultimate Power)

What if you want to sort something complex? For example, sorting a list of students by their *marks*, but if two students have the same marks, sort them by their *names* alphabetically?

You can write your own rule book using a **Custom Comparator**! 

A comparator is just a boolean function that takes two elements (let's call them `a` and `b`) and returns `true` if `a` should come strictly **before** `b`.

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

// Sort rule: Return true if 'a' should be placed before 'b'
bool myCustomRule(int a, int b) {
    // Let's sort completely based on the LAST DIGIT of the numbers!
    int lastDigitA = a % 10;
    int lastDigitB = b % 10;
    
    return lastDigitA < lastDigitB;
}

int main() {
    vector<int> v = {24, 11, 58, 42, 99};
    
    // Pass the rule as the 3rd argument
    sort(v.begin(), v.end(), myCustomRule);
    
    // Output: 11 42 24 58 99
    // (Sorted by last digits: 1, 2, 4, 8, 9)
    return 0;
}
```

### Modern C++ Shortcut: Lambda Functions
Writing a separate global boolean function for every custom sort can get tedious during a fast-paced contest. You can use an inline **Lambda function** to keep your code clean and local:

```cpp
// The exact same sorting logic, written inline!
sort(v.begin(), v.end(), [](int a, int b) {
    return (a % 10) < (b % 10);
});
```

> 💡 **Pro Tip:** Your custom comparator must return `false` if `a` and `b` are exactly equal according to your rule. Returning `true` for equal elements will cause a runtime crash!

---

## 5. Stable Sort

Imagine you sort a list of emails by their received date. Later, you sort that *same* list by the sender's name.
If you use standard `sort()`, emails from the same sender might get jumbled out of their date order. 

If you use **`stable_sort()`**, it guarantees that elements which are considered "equal" (like emails from the same sender) will **keep their original relative order**.

```cpp
// Usage is exactly the same as sort()
stable_sort(v.begin(), v.end());
```
In competitive programming, you rarely need `stable_sort()`, but it's crucial for real-world software engineering when dealing with multiple layers of sorting!

</READING_WIDGET>
