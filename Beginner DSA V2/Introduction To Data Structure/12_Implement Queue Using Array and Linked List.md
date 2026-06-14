<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Implementing a Queue: Arrays vs. Linked Lists

Imagine waiting in line to buy tickets for a blockbuster movie. The person who arrived first gets to buy their ticket first. If you arrive last, you have to stand at the very back of the line and wait for everyone in front of you to finish.

This is exactly how a **Queue** data structure works! It follows the **FIFO** (First-In, First-Out) principle. You enter at the **rear** (Enqueue) and leave from the **front** (Dequeue).

Just like stacks, we can build queues using either **Arrays** or **Linked Lists**. However, as we'll see, using an array for a queue introduces some tricky and expensive problems! Let's explore both approaches.

---

## 1. Implementing a Queue Using an Array

To implement a queue using a standard fixed-size array, we need to keep track of a few things:
1. An integer array (`arr`) to store the elements.
2. A `capacity` variable to track the maximum number of elements the queue can hold.
3. A `size` variable to track the current number of elements inside the queue.

### Core Operations

- **Enqueue (Insert)**: Add an element to the back of the queue (at index `size`). If `size == capacity`, the queue is full (**Queue Overflow**).
  - *Time Complexity*: `O(1)`
- **Dequeue (Remove)**: Remove the element at the front of the queue (at index `0`). However, because it's an array, removing index `0` leaves an empty gap at the beginning! To fix this, we must **shift every single remaining element one position to the left**. If `size == 0`, the queue is empty (**Queue Underflow**).
  - *Time Complexity*: `O(N)` 🚨 *(Due to shifting)*
- **getFront / getRear**: Return the elements at index `0` and index `size - 1` respectively.
  - *Time Complexity*: `O(1)`

### Code Implementation (Simple Array Queue)

```cpp
#include <iostream>
using namespace std;

class ArrayQueue {
    int* arr;
    int capacity;
    int size;

public:
    ArrayQueue(int c) {
        capacity = c;
        arr = new int[capacity];
        size = 0;
    }

    // Enqueue: Adds an element to the rear
    void enqueue(int x) {
        if (size == capacity) {
            cout << "Queue Overflow!\n";
            return;
        }
        arr[size] = x;
        size++;
    }

    // Dequeue: Removes the front element (Requires shifting!)
    void dequeue() {
        if (size == 0) {
            cout << "Queue Underflow!\n";
            return;
        }
        // Shift all elements one step to the left
        for (int i = 1; i < size; i++) {
            arr[i - 1] = arr[i];
        }
        size--;
    }

    // Get Front
    int getFront() {
        if (size == 0) {
            cout << "Queue is empty!\n";
            return -1;
        }
        return arr[0];
    }

    // Get Rear
    int getRear() {
        if (size == 0) {
            cout << "Queue is empty!\n";
            return -1;
        }
        return arr[size - 1];
    }
};
```

> 🚨 **The Terrible `O(N)` Limitation:** Did you notice that `dequeue()` uses a `for` loop? Shifting every element in an array takes `O(N)` time. This is painfully slow! In the real world, if we *must* use an array for a queue (to take advantage of CPU caching), we use a clever technique called a **Circular Queue** to ensure both enqueue and dequeue are `O(1)`. But for now, let's look at a much simpler way to get `O(1)` speed!

---

## 2. Implementing a Queue Using a Linked List

A linked list provides a far superior and simpler approach to building a basic queue. Because a queue modifies both ends of the data (inserting at the back, deleting from the front), we just need to maintain **two pointers** on our linked list:
1. `front`: Points to the head of the linked list (used for Dequeue).
2. `rear`: Points to the tail of the linked list (used for Enqueue).

### Why use a Linked List?
- **No shifting required**: We just rewire a pointer to remove the front element, leaving the rest of the queue untouched!
- **Fast operations**: Both Enqueue and Dequeue are strictly `O(1)` time complexity.
- **Dynamic Size**: No need to define a maximum `capacity` like we do in arrays!

### Code Implementation (Linked List Queue)

```cpp
#include <iostream>
using namespace std;

// Defining the Linked List Node
class Node {
public:
    int data;
    Node* next;
    
    Node(int new_data) {
        data = new_data;
        next = nullptr;
    }
};

class LinkedListQueue {
private:
    Node* front;  // Points to the first element
    Node* rear;   // Points to the last element
    int currSize; // Tracks the number of elements

public:
    LinkedListQueue() {
        front = nullptr;
        rear = nullptr;
        currSize = 0;
    }

    bool isEmpty() {
        return front == nullptr;
    }

    // Enqueue: Add to the rear (O(1))
    void enqueue(int new_data) {
        Node* newNode = new Node(new_data);
        
        // If queue is empty, the new node is both front and rear
        if (isEmpty()) {
            front = rear = newNode;
        } else {
            // Add the new node to the end and update the rear pointer
            rear->next = newNode;
            rear = newNode;
        }
        currSize++;
    }

    // Dequeue: Remove from the front (O(1))
    int dequeue() {
        if (isEmpty()) {
            cout << "Queue Underflow!\n";
            return -1;
        }
        
        Node* temp = front;
        int removedData = temp->data;
        
        // Move front to the next node
        front = front->next;
        
        // If the queue becomes empty after dequeue, rear must also become nullptr
        if (front == nullptr) {
            rear = nullptr;
        }
        
        delete temp; // Free memory!
        currSize--;
        
        return removedData;
    }

    // Get Front (O(1))
    int getFront() {
        if (isEmpty()) {
            cout << "Queue is empty!\n";
            return -1;
        }
        return front->data;
    }

    // Get Size
    int size() {
       return currSize;
    }
};
```

> 💡 **Core Insight:** A Linked List is the most natural and efficient way to implement a basic Queue. By managing both ends (`front` and `rear`) with simple pointers, it entirely eliminates the disastrous `O(N)` array shifting problem and ensures blazing-fast `O(1)` operations across the board!

</READING_WIDGET>
