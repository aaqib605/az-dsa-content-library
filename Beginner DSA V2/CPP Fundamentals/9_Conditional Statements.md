<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Conditional Statements

Up until now, your code has run sequentially: line 1, then line 2, then line 3. But real-world problems require **decisions**. 
What if you only want to print "Even" if a number is divisible by 2? What if you want to give a discount only if the user is a VIP? 

This is where **Conditional Statements** come into play!

---

## 1. The `if` Statement

The `if` statement evaluates a condition. If the condition is `true`, the code inside the curly braces `{}` executes. If it's `false`, the program simply skips that block of code.

```cpp
int score = 85;

// The condition goes inside parentheses ()
if (score >= 80) {
    cout << "You passed the test!\n";
}
```

## 2. The `else` Statement

What if you want to do something when the condition is *not* met? You use the `else` statement. It acts as a fallback or a default action.

```cpp
int age = 16;

if (age >= 18) {
    cout << "You are eligible to vote.\n";
} else {
    cout << "You are too young to vote.\n";
}
```

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/50a8eb81-3e3b-4d01-8da1-67c0cf5879ff.png" alt="If Else Flowchart" style="max-width: 100%; height: auto;" identifier="az-img-upload">

## 3. The `else if` Ladder

When you have multiple, mutually exclusive conditions to check, you can chain them together using `else if`. The program will evaluate them from top to bottom and execute **only the first one** that is true.

```cpp
int marks = 75;

if (marks >= 90) {
    cout << "Grade: A\n";
} else if (marks >= 80) {
    cout << "Grade: B\n";
} else if (marks >= 70) {
    cout << "Grade: C\n";
} else {
    // If none of the above are true
    cout << "Grade: F\n";
}
```

> 💡 **Pro Tip:** The order of conditions matters! If we put `marks >= 70` at the very top, a student with 95 marks would get a 'C' because that first condition evaluates to `true` and the rest of the ladder is completely skipped!

## 4. Nested Conditions

You can place `if` statements *inside* other `if` statements. This is called nesting, and it's used when a decision depends on a previous decision.

```cpp
int number = 10;

if (number > 0) {
    cout << "The number is positive.\n";
    
    // Nested check
    if (number % 2 == 0) {
        cout << "It is also an even number.\n";
    } else {
        cout << "It is an odd number.\n";
    }
} else {
    cout << "The number is zero or negative.\n";
}
```

## 5. The Ternary Operator (Shortcut)

For very simple `if-else` assignments, C++ provides a sleek one-liner called the **Ternary Operator**.

**Syntax:** `condition ? value_if_true : value_if_false;`

```cpp
int a = 15;
int b = 20;

// Without Ternary
int max_val;
if (a > b) {
    max_val = a;
} else {
    max_val = b;
}

// With Ternary
int max_val_ternary = (a > b) ? a : b;
```

It reads like English: "Is `a` greater than `b`? If yes, give me `a`. Otherwise, give me `b`."

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/c795c3b5-7fcf-42c0-8a8f-d63770ac8cff.png" alt="Ternary Operator Flowchart" style="max-width: 100%; height: auto;" identifier="az-img-upload">

</READING_WIDGET>
