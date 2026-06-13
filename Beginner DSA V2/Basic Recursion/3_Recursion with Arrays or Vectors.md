<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Recursion with Arrays and Vectors

Now that you understand how the call stack works and how to compute values like factorials, let's apply recursion to actual data structures!

## Simple Recursion with Arrays/Vectors

Recursion isn't just for math or simple printing; it's an incredibly natural way to process data structures. Let's say we want to find the sum of all elements in an array.

We can think of the sum of an array as:
`Sum = (First Element) + Sum of the (Rest of the Array)`

```cpp
// BEST PRACTICE: Passing vector by reference!
int getArraySum(vector<int>& arr, int index) {
    // Base Case: If index reaches the size of the array, return 0
    if (index == arr.size()) {
        return 0; // **RETURN base case**
    }
    
    // Recursive Case: Current element + Sum of the remaining elements
    return arr[index] + getArraySum(arr, index + 1);
}
```

> 🚨 **CRITICAL C++ TRAP: Forgetting the `&` (Pass-by-Value)**
> In the code above, we correctly passed the vector **by reference** using `vector<int>& arr`. What happens if you forget the `&` and pass it **by value** (`vector<int> arr`)? 
> 
> *Every single time* the function calls itself, it will create a brand new deep copy of the entire vector! 
> - **Time Complexity:** Silently degrades from $O(N)$ to $O(N^2)$ (copying $N$ elements, $N$ times).
> - **Space Complexity:** Becomes an $O(N^2)$ Memory Limit Exceeded (MLE) disaster!
> 
> **The Takeaway:** Always pass large data structures like `std::vector` or `std::string` by reference to keep the space complexity at $O(N)$ for the call stack with no extra copying overhead!

To call this function, we would use `getArraySum(arr, 0)` starting at index 0. 

You can apply the exact same logic to strings. For example, to reverse a string or check if it's a palindrome, you compare the outer characters and recursively check the inner substring.

</READING_WIDGET>
