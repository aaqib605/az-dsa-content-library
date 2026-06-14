<VIDEO_WIDGET>

<VIDEO_ID></VIDEO_ID> <!-- Required -->

</VIDEO_WIDGET>

<READING_WIDGET>

# Introduction to Linked Lists

Imagine you're playing a massive treasure hunt game. You find a clue, and it doesn't just give you the prize—it gives you a piece of information and the exact coordinates of where to find the *next* clue. You follow the chain, clue by clue, until you reach the end. 

This is exactly how a **Linked List** works in computer science! Instead of storing everything in one massive, perfectly aligned row (like an Array), a Linked List scatters its data across memory. Each piece of data simply holds a "clue"—a pointer—telling the computer exactly where to find the next piece.

## Connection to Linear Data Structures

Like Arrays, Stacks, and Queues, a Linked List is a **Linear Data Structure**. This means the data is organized in a strict sequence. However, while arrays demand a single, continuous block of memory (which can be hard to find if your memory is highly fragmented), linked lists are incredibly flexible. They grab available memory blocks wherever they exist and magically link them all together.

> 💡 **Core Insight:** Arrays are rigid but allow instant access (like houses on a perfectly numbered street). Linked Lists are flexible but require sequential access (like following a treasure map). If you need to constantly add and remove elements without shifting everything else around, Linked Lists are your best friend!

---

## 1. Singly Linked List

In a **Singly Linked List**, each element is called a **Node**. A node contains two things:
1. The **Data** (the actual value you want to store).
2. The **Next Pointer** (the exact memory address of the next node in the chain).

The very first node is universally known as the **Head**, and the very last node points to `NULL` to signify the absolute end of the chain.

<img src="https://d3pdqc0wehtytt.cloudfront.net/academy-media/62/a7b10c0d-de88-446c-9e15-85d9b4a11b8e.png" alt="Singly Linked List Diagram" style="max-width: 100%; height: auto;" identifier="az-img-upload">

### Creating a Singly Linked List

Here is how you define and create a simple singly linked list in C++:

```cpp
#include <iostream>
using namespace std;

// Defining the Node structure
struct Node {
    int data;       // The value
    Node* next;     // Pointer to the next node

    // Constructor to easily create a new node
    Node(int val) {
        data = val;
        next = nullptr;
    }
};

int main() {
    // 1. Create the standalone nodes
    Node* head = new Node(10);
    Node* second = new Node(20);
    Node* third = new Node(30);

    // 2. Link them together
    head->next = second;
    second->next = third;

    return 0;
}
```

### Operations on a Singly Linked List

Let's dive into how we manipulate a Singly Linked List.

#### Traversal
Traversal is the act of visiting every single node in the list. Start at the `head` and hop to the `next` pointer until you hit `NULL`.
- *Time Complexity*: `O(N)` (You have to visit $N$ elements).

```cpp
// Traverse and print the list
void traverseList(Node* head) {
    Node* temp = head;
    while (temp != nullptr) {
        cout << temp->data << " -> ";
        temp = temp->next; // Move to the next node
    }
    cout << "NULL" << endl;
}
```

#### Insertion

**At the Front (Head)**
Make the new node's `next` point to the current `head`, and then update the `head` to be the new node.
- *Time Complexity*: `O(1)` (Instant! No shifting needed).

```cpp
void insertAtFront(Node*& head, int val) {
    Node* newNode = new Node(val);
    newNode->next = head;
    head = newNode;
}
```

**At the Back (Tail)**
Traverse the list to find the very last node, and make its `next` point to the new node. 
- *Time Complexity*: `O(N)` (Because you have to traverse to find the tail).

```cpp
void insertAtBack(Node*& head, int val) {
    Node* newNode = new Node(val);
    if (head == nullptr) {
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }
    temp->next = newNode;
}
```

**At Any Specific Position (0-indexed)**
Traverse the list to the node *just before* the desired position. Rewire the previous node's `next` to point to the new node, and the new node's `next` to point to the rest of the chain.
- *Time Complexity*: `O(N)` (Due to traversal).

```cpp
void insertAtPosition(Node*& head, int val, int pos) {
    if (pos == 0) {
        insertAtFront(head, val);
        return;
    }
    Node* newNode = new Node(val);
    Node* temp = head;
    for (int i = 0; temp != nullptr && i < pos - 1; i++) {
        temp = temp->next;
    }
    if (temp == nullptr) return; // Position out of bounds
    
    newNode->next = temp->next;
    temp->next = newNode;
}
```

#### Deletion

**At the Front (Head)**
Simply move the `head` pointer to `head->next` and delete the old head.
- *Time Complexity*: `O(1)`

```cpp
void deleteFront(Node*& head) {
    if (head == nullptr) return;
    Node* toDelete = head;
    head = head->next;
    delete toDelete;
}
```

**At the Back (Tail)**
You must traverse the entire list to find the *second to last* node, change its `next` to `nullptr`, and delete the last node.
- *Time Complexity*: `O(N)`

```cpp
void deleteBack(Node*& head) {
    if (head == nullptr) return;
    if (head->next == nullptr) {
        delete head;
        head = nullptr;
        return;
    }
    Node* temp = head;
    while (temp->next->next != nullptr) {
        temp = temp->next;
    }
    delete temp->next;
    temp->next = nullptr;
}
```

**At Any Specific Position**
Traverse to the node *just before* the one you want to delete. Change its `next` pointer to skip over the target node.
- *Time Complexity*: `O(N)`

```cpp
void deleteAtPosition(Node*& head, int pos) {
    if (head == nullptr) return;
    if (pos == 0) {
        deleteFront(head);
        return;
    }
    Node* temp = head;
    for (int i = 0; temp != nullptr && i < pos - 1; i++) {
        temp = temp->next;
    }
    if (temp == nullptr || temp->next == nullptr) return; // Out of bounds
    
    Node* toDelete = temp->next;
    temp->next = temp->next->next;
    delete toDelete;
}
```

---

## 2. Doubly Linked List

What if you're on a treasure hunt, but you drop your compass and need to walk backward to the previous clue? A Singly Linked List can't help you—it only goes forward!

Enter the **Doubly Linked List**. In this structure, every node is upgraded to contain *three* things:
1. The **Data**.
2. A **Next Pointer** (pointing forward).
3. A **Prev Pointer** (pointing backward).

This allows you to traverse the list in both directions, giving you ultimate flexibility!

<img src="https://d3pdqc0wehtytt.cloudfront.net/academy-media/62/28408e41-8319-4239-a5b5-e6f278fa11c4.png" alt="Doubly Linked List Diagram" style="max-width: 100%; height: auto;" identifier="az-img-upload">

### Creating a Doubly Linked List

```cpp
#include <iostream>
using namespace std;

// Defining the Doubly Linked Node structure
struct DoublyNode {
    int data;
    DoublyNode* next;
    DoublyNode* prev;

    DoublyNode(int val) {
        data = val;
        next = nullptr;
        prev = nullptr;
    }
};

int main() {
    // 1. Create the nodes
    DoublyNode* head = new DoublyNode(10);
    DoublyNode* second = new DoublyNode(20);
    DoublyNode* third = new DoublyNode(30);

    // 2. Link them together (Both forward and backward!)
    head->next = second;
    
    second->prev = head;
    second->next = third;

    third->prev = second;

    return 0;
}
```

### Operations on a Doubly Linked List

Doubly linked lists require slightly more pointer rewiring (to keep the `prev` pointers aligned), but offer much better versatility.

#### Traversal
You can start at the `head` and go forward using `next`, OR start at the `tail` and go backward using `prev`. 
- *Time Complexity*: `O(N)`.

```cpp
// Traverse backward starting from a known node!
void traverseBackward(DoublyNode* tail) {
    DoublyNode* temp = tail;
    while (temp != nullptr) {
        cout << temp->data << " <-> ";
        temp = temp->prev; // Move backwards!
    }
    cout << "NULL" << endl;
}
```

#### Insertion

**At the Front (Head)**
Make the new node's `next` point to the current `head`, and update the old head's `prev` pointer. Finally, update the `head` to be the new node.
- *Time Complexity*: `O(1)`

```cpp
void insertAtFrontDoubly(DoublyNode*& head, int val) {
    DoublyNode* newNode = new DoublyNode(val);
    newNode->next = head;
    if (head != nullptr) {
        head->prev = newNode;
    }
    head = newNode;
}
```

**At the Back (Tail)**
Traverse the list to find the very last node, and make its `next` point to the new node, and the new node's `prev` to point to the last node.
- *Time Complexity*: `O(N)` (Because we must traverse to find the tail).

```cpp
void insertAtBackDoubly(DoublyNode*& head, int val) {
    DoublyNode* newNode = new DoublyNode(val);
    if (head == nullptr) {
        head = newNode;
        return;
    }
    DoublyNode* temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
}
```

**At Any Specific Position**
Traverse to the node *just before* the desired position. Rewire the four affected pointers carefully.
- *Time Complexity*: `O(N)` (Due to traversal).

```cpp
void insertAtPositionDoubly(DoublyNode*& head, int val, int pos) {
    if (pos == 0) {
        insertAtFrontDoubly(head, val);
        return;
    }
    DoublyNode* newNode = new DoublyNode(val);
    DoublyNode* temp = head;
    for (int i = 0; temp != nullptr && i < pos - 1; i++) {
        temp = temp->next;
    }
    if (temp == nullptr) return; // Position out of bounds

    newNode->next = temp->next;
    if (temp->next != nullptr) {
        temp->next->prev = newNode;
    }
    temp->next = newNode;
    newNode->prev = temp;
}
```

#### Deletion

**At the Front (Head)**
Move the `head` pointer to `head->next`, ensure its `prev` pointer is set to `nullptr`, and delete the old head.
- *Time Complexity*: `O(1)`

```cpp
void deleteFrontDoubly(DoublyNode*& head) {
    if (head == nullptr) return;
    DoublyNode* toDelete = head;
    head = head->next;
    if (head != nullptr) {
        head->prev = nullptr;
    }
    delete toDelete;
}
```

**At the Back (Tail)**
Traverse to the end, step back using the `prev` pointer, set the second-to-last node's `next` to `nullptr`, and delete the tail.
- *Time Complexity*: `O(N)` (Because we don't have a global tail pointer).

```cpp
// Without a global tail pointer
void deleteBackDoubly(DoublyNode*& head) {
    if (head == nullptr) return;
    if (head->next == nullptr) {
        delete head;
        head = nullptr;
        return;
    }
    DoublyNode* temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }
    temp->prev->next = nullptr;
    delete temp;
}
```

**At Any Specific Position**
Traverse to the node *just before* the one you want to delete. Rewire the pointers to completely skip over the target node in both directions.
- *Time Complexity*: `O(N)`

```cpp
void deleteAtPositionDoubly(DoublyNode*& head, int pos) {
    if (head == nullptr) return;
    if (pos == 0) {
        deleteFrontDoubly(head);
        return;
    }
    DoublyNode* temp = head;
    for (int i = 0; temp != nullptr && i < pos - 1; i++) {
        temp = temp->next;
    }
    if (temp == nullptr || temp->next == nullptr) return; // Out of bounds
    
    DoublyNode* toDelete = temp->next;
    temp->next = toDelete->next;
    if (toDelete->next != nullptr) {
        toDelete->next->prev = temp;
    }
    delete toDelete;
}
```

> 💡 **Core Insight:** Doubly Linked Lists take up slightly more memory (because of the extra `prev` pointer), but they make certain operations much faster and easier—especially deleting the tail if you explicitly keep track of a `tail` pointer!

---

## A Note on C++ STL (`std::list` & `std::forward_list`)

While it is absolutely crucial to know how to build a linked list from scratch for interviews, you rarely have to reinvent the wheel in real-world production or competitive programming! The C++ Standard Template Library (STL) actually provides built-in linked lists:

- `std::list`: This is implemented as a **Doubly Linked List** under the hood. It allows you to traverse in both directions and seamlessly push/pop elements from both the front and back in `O(1)` time.
- `std::forward_list`: This is implemented as a **Singly Linked List**. It is highly memory-efficient since it only uses one pointer, but it only allows forward traversal.

```cpp
#include <iostream>
#include <list>
using namespace std;

int main() {
    list<int> myList; // A built-in Doubly Linked List!

    myList.push_back(10);  // Insert at back O(1)
    myList.push_front(20); // Insert at front O(1)

    // Traversal is incredibly easy using iterators or range-based for loops!
    for (int val : myList) {
        cout << val << " <-> ";
    }
    cout << "NULL\n";

    return 0;
}
```

</READING_WIDGET>
