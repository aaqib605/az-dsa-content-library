---
title: "Strings"
slug: "strings"
track: "beginner-dsa"
level: "Beginner"
order: 8
status: "Draft"
duration: ""
videoStatus: "Not Published"
updatedAt: "2026-05-14"
description: "Master text manipulation in C++ by learning how to declare, traverse, modify, and compare strings."
---

# Strings

You now know how to store a collection of numbers using arrays. But what if you want to store a word or a sentence, like `"AlgoZenith"`? 
Technically, a word is just a collection (array) of single characters (`char`).

In C++, instead of forcing you to make an `array of chars`, we have a much more powerful and flexible tool: **The `string`**.

---

## 1. What is a String?

A `string` is a special object in C++ that holds a sequence of characters. To use them effectively, you just need `#include <string>` (or our magic `#include <bits/stdc++.h>`).

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string greeting = "Hello";
    return 0;
}
```

![A visual showing the word 'Hello' broken down into 5 contiguous blocks with indices 0 to 4](../Images/string_indexing.png)

---

## 2. Input and Output

### Basic Input (`cin`)
Using `cin` with a string will read a **single word**. It stops reading the moment it hits a space or a new line.

```cpp
string name;
cin >> name; // If you type "Vivek Gupta", it only stores "Vivek"
cout << name;
```

### Reading a Full Sentence (`getline`)
If you want to read an entire line of text (including the spaces), you use the `getline()` function.

```cpp
string fullName;
// Reads the whole line until you press Enter
getline(cin, fullName); 
cout << fullName; // Prints "Vivek Gupta" perfectly!
```

---

## 3. String Length and Indexing

Strings behave exactly like arrays under the hood. They use **0-based indexing**, meaning the first character is at index `0`.

### Finding the Length
You can find out how many characters are in a string using `.length()` or `.size()`.

```cpp
string s = "Apple";
cout << "Length: " << s.length() << "\n"; // Prints 5
```

### Accessing and Updating Characters
You can read or change individual characters using square brackets `[]`, just like an array!

```cpp
string fruit = "Apple";
cout << fruit[0]; // Prints 'A'

// Let's modify the string!
fruit[0] = 'a'; 
cout << fruit; // Prints "apple"
```

> ⚠️ **Warning:** Strings use double quotes (`"text"`), but single characters use single quotes (`'A'`). When updating `fruit[0]`, you MUST use single quotes!

---

## 4. Traversing a String

Since strings are basically arrays, we can loop through them to look at each character one by one.

### Using a Standard `for` Loop
```cpp
string s = "Code";
for (int i = 0; i < s.length(); i++) {
    cout << s[i] << "-";
}
// Output: C-o-d-e-
```

### Using the Range-Based `for` Loop
If you just want to read the characters without caring about their index, this is the cleanest way:

```cpp
string s = "Code";
for (char c : s) {
    cout << c << " ";
}
// Output: C o d e
```

---

## 5. Comparing Strings

One of the best things about C++ strings is that you can compare them directly using standard operators (`==`, `!=`, `<`, `>`).

- `==` checks if they are exactly identical.
- `<` and `>` compare them **lexicographically** (Dictionary order).
  - `"Apple"` comes before `"Banana"` in the dictionary, so `"Apple" < "Banana"` is `true`.

```cpp
string s1 = "Cat";
string s2 = "Dog";

if (s1 == s2) {
    cout << "Same words\n";
} else if (s1 < s2) {
    cout << s1 << " comes first in the dictionary!\n"; // This prints!
}
```

---

## 6. Basic String Operations

### Concatenation (Adding Strings Together)
You can easily glue strings together using the `+` operator.

```cpp
string a = "Algo";
string b = "Zenith";

string combined = a + b; // "AlgoZenith"
combined += "!";       // "AlgoZenith!"
```

### Substrings
You can extract a smaller piece of a string using `.substr(starting_index, length)`.

```cpp
string s = "Competitive Programming";
string sub = s.substr(0, 11); // Start at index 0, take 11 characters
cout << sub; // Prints "Competitive"
```

---

## Let's Practice!

Strings are incredibly common in interview questions. Master the basics with these problems!

Try solving the following problems:
- **[Create A New String](https://codeforces.com/group/MWSDmqGsZm/contest/219856/problem/A)**
- **[Let's use Getline](https://maang.in/problems/Lets-Use-Getline-1184)**
- **[Compare](https://maang.in/problems/Compare-1185)**
- **[Strings](https://maang.in/problems/Strings-1186)**
- **[Count](https://maang.in/problems/Count-1187)**
- **[Count Letters](https://maang.in/problems/Count-Letters-1191)**
- **[Way Too Long Words](https://maang.in/problems/Way-Too-Long-Words-1188)**
- **[Conversion](https://codeforces.com/group/MWSDmqGsZm/contest/219856/problem/G)**
- **[String Functions](https://maang.in/problems/String-Functions-1193)**
- **[Reverse Words](https://maang.in/problems/Reverse-Words-1198)**
- **[Count Words](https://maang.in/problems/Count-Words-1197)**
- **[Good Or Bad](https://maang.in/problems/Good-Or-Bad-1189)**
- **[I Love Strings](https://maang.in/problems/I-Love-Strings-1192)**

---

## Video Explanation

[![Strings](../Images/video-lecture-thumbnail.jpg)]()
