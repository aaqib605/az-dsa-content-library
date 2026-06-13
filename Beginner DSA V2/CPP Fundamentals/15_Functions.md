<VIDEO_WIDGET>

<VIDEO_ID>3438</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Functions: Just Enough to Organize Code

As the problems you solve get harder, your `main()` function will start getting longer and messier.
Imagine writing a 500-line program where everything is stuffed inside `main()`. If there's a bug, finding it will be a nightmare!

To keep our code clean, readable, and reusable, we use **Functions**.

---

## 1. Why are Functions Useful?

Think of a function as a **mini-program** or a **machine**.
You give the machine some raw materials (Inputs), the machine does a specific job, and it hands you back a finished product (Output).

**Benefits:**

- **Reusability (DRY - Don't Repeat Yourself):** Write the logic once, use it 100 times.
- **Readability:** `int mx = findMax(a, b);` is much easier to read than writing the comparison logic repeatedly.
- **Debugging:** If finding the maximum is broken, you only have to fix the `findMax` function, not 50 different places in your code.

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/2a3c8fe8-42be-4416-8168-edb8883c4ae2.png" alt="Function Machine" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## 2. Function Syntax

To build a function in C++, you need to define three main things:

1. **Return Type:** What kind of data will this machine give back? (e.g., `int`, `bool`, `string`)
2. **Name:** What is the machine called?
3. **Parameters:** What raw materials does it need to do its job?

```cpp
// ReturnType Name(Parameters)
int addNumbers(int a, int b) {
    int sum = a + b;
    return sum; // This is the final product handed back
}
```

---

## 3. Parameters and Return Values

Let's look at how we actually _use_ (or **call**) the function we just created.

```cpp
#include <iostream>
using namespace std;

// Function definition must be ABOVE main()
int addNumbers(int a, int b) {
    return a + b;
}

int main() {
    // Calling the function and storing the result
    int result = addNumbers(10, 5);
    cout << "The sum is: " << result << "\n";

    // You can call it as many times as you want!
    cout << "Another sum: " << addNumbers(100, 200) << "\n";

    return 0;
}
```

> 💡 **Pro Tip:** What if you _really_ want to write your function below `main()`? You can use a **Function Prototype**! Just write the function's declaration (like `int addNumbers(int a, int b);`) at the very top of your file to warn the compiler that the function exists, and then write the actual body below `main()`.

---

## 4. `void` Functions (When You Don't Need an Output)

Sometimes, a machine just performs an action and doesn't give anything back. For example, a function that just prints a greeting.
In this case, we use the `void` return type. A `void` function does not need a `return` statement.

```cpp
void sayHello(string name) {
    cout << "Hello there, " << name << "!\n";
}

int main() {
    sayHello("AlgoZenith"); // It prints directly to the screen
    return 0;
}
```

---

## 5. Local Variables

A critical concept to understand is **Scope**.
Variables created _inside_ a function are **Local Variables**. They only exist while that specific function is running. Once the function finishes, those variables are destroyed.

The `main()` function cannot see variables created inside `addNumbers()`, and vice versa!

```cpp
#include <iostream>
using namespace std;

int secret = 100; // Global variable (can be seen by everyone)

void doMath() {
    int secret = 42; // Local variable (SHADOWS the global variable)
    cout << "Inside doMath, secret is: " << secret << "\n"; // Prints 42
}

int main() {
    cout << "Inside main, before doMath, secret is: " << secret << "\n"; // Prints 100
    doMath();
    cout << "Inside main, after doMath, secret is: " << secret << "\n"; // Still prints 100!
    return 0;
}
```

> 💡 **Pro Tip:** As you can see above, naming a local variable the same thing as a global variable causes "Shadowing." The local variable temporarily hides the global one while you are inside that function, which can lead to incredibly frustrating bugs!

---

## 6. Basic Helper Functions in Action

In Competitive Programming, we often use helper functions to keep `main()` completely clean. Here is a classic example: a helper function to check if a number is prime.

```cpp
#include <iostream>
using namespace std;

// Helper function
bool isPrime(int n) {
    if (n <= 1) return false;
    for (int i = 2; i * i <= n; i++) {
        if (n % i == 0) {
            return false; // We found a divisor, not prime!
        }
    }
    return true; // No divisors found, it is prime!
}

int main() {
    int number;
    cin >> number;

    // Look how clean main() is!
    if (isPrime(number)) {
        cout << "Yes, it is a prime number.\n";
    } else {
        cout << "No, it is not prime.\n";
    }

    return 0;
}
```

</READING_WIDGET>
