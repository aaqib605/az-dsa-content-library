<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Introduction to Recursion

Hey there! Have you ever looked at two mirrors facing each other and seen an infinite tunnel of reflections? That's recursion in real life! In programming, recursion is one of the most powerful and elegant techniques you can learn. If you can master recursion, you're halfway to mastering Data Structures and Algorithms.

Let's demystify recursion step by step so you can start thinking recursively!

## What is Recursion?

At its core, **recursion is simply a function that calls itself** to solve smaller instances of the same problem. 

Think of a large task, like eating a giant pizza. You don't eat it all at once; you take a bite, and then what's left is a slightly smaller pizza. You repeat the process (take a bite, get a smaller pizza) until the pizza is gone. Recursion works exactly the same way.

> 💡 **Interview Insight:** Many advanced topics like Trees, Graphs, and Dynamic Programming rely heavily on recursion. If you can't confidently trace a recursive function, you'll struggle in DSA interviews. Spend extra time building your intuition here!

<img src="https://d3pdqc0wehtytt.cloudfront.net/media/9651/c15f429e-4a7a-4038-9db2-b0d92c5ec0d4.png" alt="Recursion Tree" style="max-width: 100%; height: auto;" identifier="az-img-upload">

---

## Function Calling Itself

Let's look at a simple example of a function calling itself in C++:

```cpp
void sayHello() {
    cout << "Hello!\n";
    sayHello(); // The function calls itself!
}
```

If you run this code, it will print "Hello!" over and over again until your program crashes. Why? Because we didn't tell it when to stop! This is called **infinite recursion**, and it's the recursive equivalent of an infinite loop.

To prevent this, every recursive function needs two crucial parts: the **Base Case** and the **Recursive Case**.

---

## The Base Case and Recursive Case

### The Base Case (How recursive calls stop)
The base case is the condition under which the function **stops** calling itself. It prevents the infinite loop and tells the recursion when the task is small enough to be solved directly.

### The Recursive Case
The recursive case is the part of the function where it actually calls itself, breaking the main problem into a smaller, simpler sub-problem.

Let's write a function to print "Hello" exactly 3 times using these concepts:

```cpp
void sayHello(int times) {
    // 1. Base Case: Stop when there are no more times left
    if (times == 0) {
        return; // **RETURN to stop the recursion!**
    }
    
    // 2. Do the work for the current step
    cout << "Hello!\n";
    
    // 3. Recursive Case: Call the function with a smaller problem
    sayHello(times - 1); 
}
```

When we call `sayHello(3)`, it works perfectly. But how exactly does the computer keep track of all these nested function calls? We'll uncover that mystery in the next lesson when we dive into the **Call Stack**!

</READING_WIDGET>