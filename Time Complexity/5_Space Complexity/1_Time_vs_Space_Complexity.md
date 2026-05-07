# Time Complexity vs. Space Complexity

Throughout this guide, we've been obsessed with **Time Complexity**—how _fast_ an algorithm runs. But that is only half of the story in Data Structures and Algorithms. The other half is **Space Complexity**.

## Speed vs. Memory

- **Time Complexity:** How much _time_ (or how many operations) your code needs to execute as the input $N$ grows.
- **Space Complexity:** How much _memory_ (RAM) your code needs to execute as the input $N$ grows.

When we talk about Space Complexity, there are two distinct terms you should know:

1. **Auxiliary Space:** The _extra_ or temporary space used by your algorithm (like creating a new array or using a Hash Map).
2. **Total Space:** The Auxiliary Space + the space taken by the input itself.

> 💡 **Interview Insight:** In interviews, when they ask for "Space Complexity", they almost always mean **Auxiliary Space**. They want to know how much _extra_ memory your specific algorithm consumes, ignoring the data that was handed to you.

Just like Time Complexity, Space Complexity is measured using Big O notation!

**Example of $O(1)$ Space (Constant Space):**

```cpp
int sum(vector<int>& arr) {
    int total = 0; // We only created one integer variable
    for(int x : arr) total += x;
    return total;
}
```

No matter how massive the array gets, we only use a tiny, fixed amount of extra memory for the `total` variable.

**Example of $O(N)$ Space (Linear Space):**

```cpp
vector<int> copyArray(vector<int>& arr) {
    vector<int> newArr; // We are creating a brand new array!
    for(int x : arr) newArr.push_back(x);
    return newArr;
}
```

If the input array has 1,000,000 elements, we need memory to store 1,000,000 _new_ elements. The space requirement grows directly with $N$.

## The Classic Trade-Off: Why Both Matter

In the real world, memory is finite. If you are writing software for a tiny smartwatch, you might not care if an app takes an extra second to load, but you _definitely_ care if it crashes the watch because it ran out of memory!

In competitive programming and interviews, you are often faced with a **Time-Space Trade-off**.

- You can often make an algorithm **faster** (better time complexity) by using a Hash Map or an extra array to store pre-computed results. But this costs memory (worse space complexity).
- You can **save memory** by doing calculations on the fly without storing anything, but this often requires nested loops (worse time complexity).

> 💡 **Interview Insight:** A great engineer doesn't just blindly write the fastest code. A great engineer asks the interviewer: _"I can solve this in $O(N)$ time but it will take $O(N)$ extra space. Or, I can do it in $O(N \log N)$ time using $O(1)$ space. Which resource is more restricted in our system, memory or CPU?"_

---

**Congratulations!** You've made it through the ultimate guide to Time Complexity. You are now equipped to look at any code and know exactly how fast it will run, and look at any problem constraints and know exactly what algorithm to write. Happy Coding!

## Video Explanation

[![Introduction to Time Complexity](Images/video-lecture-thumbnail.jpg)](https://drive.google.com/file/d/181UJxokpFh4UukYYIUdHoTfQ6ZqnMNh0/view?usp=sharing)
