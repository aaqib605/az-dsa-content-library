<VIDEO_WIDGET>

<VIDEO_ID>3434</VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Input, Output, and Online Judge Format

When solving algorithmic problems, your program acts like a factory: it takes raw materials (**Input**), processes them, and produces a finished product (**Output**).
In C++, handling input and output is incredibly easy and intuitive thanks to "streams." Let's dive in!

---

## 1. Printing Output: `cout`

To print anything to the screen, we use `cout` (pronounced "see-out", meaning Console Output) along with the insertion operator `<<`.

```cpp
#include <iostream>
using namespace std;
int main() {
    cout << "Hello, AlgoZenith!";
    return 0;
}
```

You can print multiple things at once by chaining the `<<` operator:

```cpp
cout << "I am " << "20 years old.";
// Output: I am 20 years old.
```

### The Newline Battle: `\n` vs `endl`

By default, C++ doesn't move to the next line after printing. To force a new line, you have two options:

1. `\n` (Newline character)
2. `endl` (End Line manipulator)

```cpp
cout << "Line 1\n";
cout << "Line 2" << endl;
```

> 💡 **Pro Tip:** In Competitive Programming, **always use `\n` instead of `endl`**.
> The `endl` command does two things: it prints a new line AND "flushes" the output stream. Flushing forces the computer to write everything to the screen immediately, which is a very slow operation. If you print 100,000 lines using `endl`, your code might get a **Time Limit Exceeded (TLE)** just because of printing!

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/d67c48a4-de54-4761-8126-0b4ba5152b9b.png" alt="Newline Vs Endl" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## 2. Taking Input: `cin`

To take input from the user (or the Online Judge), we use `cin` (pronounced "see-in", meaning Console Input) along with the extraction operator `>>`.

```cpp
int x;
cin >> x; // Reads an integer into variable x
```

### Reading Multiple Values

You don't need to write multiple `cin` statements. You can chain the `>>` operator just like we did with `cout`. `cin` is smart enough to automatically skip spaces and newlines!

```cpp
int a, b;
// If the input is "10 20" or
// "10
//  20",
// this single line handles both perfectly!
cin >> a >> b;
cout << "The sum is: " << a + b << "\n";
```

---

## 3. The Online Judge Format: Multiple Test Cases

Most problems on Codeforces or LeetCode are tested using multiple "test cases" at once.

The problem will say: _"The first line contains an integer T, the number of test cases. Then T test cases follow."_
Here is the standard template you will use for 99% of competitive programming problems to handle this:

```cpp
#include <iostream>
using namespace std;
int main() {
    int t;
    cin >> t; // Read the number of test cases

    // This loop runs exactly 't' times
    while(t--) {
        // Solve each test case here
        int a, b;
        cin >> a >> b;
        cout << a + b << "\n";
    }

    return 0;
}
```

Everything inside the `while(t--)` loop will execute `t` times. This lets you handle each test case one by one without restarting the program!

---

## 4. Fast I/O Basics (The Magic Spell)

Sometimes, a problem gives you a massive amount of input data (like an array of 1,000,000 numbers). C++'s standard `cin` and `cout` are slightly slow because they are synchronized with C's older `scanf` and `printf` functions for safety.

To make `cin` and `cout` as fast as the speed of light, you must cast this magic spell at the very beginning of your `main()` function:

```cpp
#include <iostream>
using namespace std;

int main() {
    // Fast I/O Magic Spell
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);

    // Now you can take input safely
    int t;
    cin >> t;
    while(t--) {
        int a, b;
        cin >> a >> b;
        cout << a + b << "\n";
    }
    return 0;
}
```

Just memorize these two lines and put them in every boilerplate template you write. You will never have to worry about input/output slowness again!

</READING_WIDGET>
