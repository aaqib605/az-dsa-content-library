# Code Examples for Time Complexity

The best way to get comfortable with Time Complexity is by looking at lots of examples! Let's go through some common code snippets you might encounter and analyze them together.

## 1. Constant Time - $O(1)$
These operations take the same amount of time regardless of how big the input is.

```cpp
// Example: Checking if a number is even
bool isEven(int n) {
    return n % 2 == 0;
}
// Complexity: O(1)
```

## 2. Linear Loops - $O(N)$
Loops that iterate through the input one by one.

```cpp
// Example: Summing an array
int getSum(vector<int>& arr) {
    int sum = 0;
    for(int i = 0; i < arr.size(); i++) {
        sum += arr[i];
    }
    return sum;
}
// Complexity: O(N)
```

## 3. Nested Loops - $O(N^2)$
Loops inside loops where both depend on $N$.

```cpp
// Example: Printing a 2D Grid
void printGrid(int n) {
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < n; j++) {
            cout << "* ";
        }
        cout << "\n";
    }
}
// Complexity: O(N^2)
```

## 4. Logarithmic Loops - $O(\log N)$
Loops that cut the problem size in half (or some fraction) at each step.

```cpp
// Example: Counting digits of a number
int countDigits(int n) {
    int count = 0;
    while(n > 0) {
        n = n / 10;
        count++;
    }
    return count;
}
// Complexity: O(log_10(N)), which simplifies to O(log N)
```

## 5. Sorting-Based Examples - $O(N \log N)$
Any algorithm that relies on efficient sorting.

```cpp
// Example: Checking for duplicates
bool hasDuplicates(vector<int>& arr) {
    // Step 1: Sort the array (Takes O(N log N))
    sort(arr.begin(), arr.end());
    
    // Step 2: Linear scan (Takes O(N))
    for(int i = 0; i < arr.size() - 1; i++) {
        if(arr[i] == arr[i+1]) return true;
    }
    return false;
}
// Complexity: O(N log N) + O(N) = O(N log N)
```

## 6. Recursion Examples
The complexity depends on how many recursive calls are made.

```cpp
// Example: Factorial (Linear Recursion)
int factorial(int n) {
    if(n <= 1) return 1;
    return n * factorial(n - 1);
}
// Complexity: O(N) (N calls, doing O(1) work each)
```

## 7. Mixed Complexity Examples
Combining different pieces together.

```cpp
void mixedExample(vector<int>& arr, int m) {
    int n = arr.size();
    
    // Part 1: O(N)
    for(int i = 0; i < n; i++) cout << arr[i];
    
    // Part 2: O(N * M)
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < m; j++) {
            cout << "Mixing!";
        }
    }
    
    // Part 3: O(N log N)
    sort(arr.begin(), arr.end());
}
// Complexity: O(N) + O(N * M) + O(N log N)
// This doesn't simplify nicely unless we know the relationship between N and M.
// Final Answer: O(N*M + N log N)
```