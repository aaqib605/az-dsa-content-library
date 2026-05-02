# Code Examples for Time Complexity

The best way to get comfortable with Time Complexity is by looking at lots of examples! Let's go through some common code snippets you might encounter and analyze them together.

## 1. Constant Time - $O(1)$
These operations take the same amount of time regardless of how big the input is.

```cpp
// Example A: Swapping two numbers
void swap(int &a, int &b) {
    int temp = a;
    a = b;
    b = temp;
}
// Complexity: O(1)

// Example B: Checking if a number is even
bool isEven(int n) {
    return n % 2 == 0;
}
// Complexity: O(1)
```

## 2. Linear Loops - $O(N)$
Loops that iterate through the input one by one.

```cpp
// Example A: Summing an array
int getSum(vector<int>& arr) {
    int sum = 0;
    for(int i = 0; i < arr.size(); i++) {
        sum += arr[i];
    }
    return sum;
}
// Complexity: O(N)

// Example B: Two pointers moving towards each other
bool isPalindrome(string s) {
    int left = 0, right = s.length() - 1;
    while(left < right) {
        if(s[left] != s[right]) return false;
        left++;
        right--;
    }
    return true;
}
// Complexity: O(N) (Even though it only checks N/2 elements, we drop the constant)
```

## 3. Nested Loops - $O(N^2)$
Loops inside loops where both depend on $N$.

```cpp
// Example A: Printing a 2D Grid
void printGrid(int n) {
    for(int i = 0; i < n; i++) {
        for(int j = 0; j < n; j++) {
            cout << "* ";
        }
        cout << "\n";
    }
}
// Complexity: O(N^2)

// Example B: Selection Sort
void selectionSort(vector<int>& arr) {
    int n = arr.size();
    for(int i = 0; i < n; i++) {
        int min_idx = i;
        for(int j = i + 1; j < n; j++) {
            if(arr[j] < arr[min_idx]) {
                min_idx = j;
            }
        }
        swap(arr[i], arr[min_idx]);
    }
}
// Complexity: O(N^2) (The inner loop runs N, then N-1, then N-2... summing to ~N^2 / 2)
```

## 4. Logarithmic Loops - $O(\log N)$
Loops that cut the problem size in half (or some fraction) at each step.

```cpp
// Example A: Counting digits of a number
int countDigits(int n) {
    int count = 0;
    while(n > 0) {
        n = n / 10;
        count++;
    }
    return count;
}
// Complexity: O(log_10(N)), which simplifies to O(log N)

// Example B: Power function (Fast Exponentiation)
long long power(long long base, long long exp) {
    long long res = 1;
    while(exp > 0) {
        if(exp % 2 == 1) res *= base;
        base *= base;
        exp /= 2;
    }
    return res;
}
// Complexity: O(log exp)
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
// Example A: Factorial (Linear Recursion)
int factorial(int n) {
    if(n <= 1) return 1;
    return n * factorial(n - 1);
}
// Complexity: O(N) (N calls, doing O(1) work each)

// Example B: Subsets/Power Set (Exponential Recursion)
void generateSubsets(string s, string current, int index) {
    if(index == s.length()) {
        cout << current << "\n";
        return;
    }
    // Take the character
    generateSubsets(s, current + s[index], index + 1);
    // Don't take the character
    generateSubsets(s, current, index + 1);
}
// Complexity: O(2^N) (Each call branches into 2 more calls)
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