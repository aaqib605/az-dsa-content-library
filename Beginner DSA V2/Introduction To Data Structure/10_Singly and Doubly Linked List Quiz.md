<READING_WIDGET>
# Singly and Doubly Linked List Quiz

Choose the correct answer for each question.
</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Unlike an Array, how does a Linked List store its data in memory?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about what happens when your computer's memory is fragmented.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        An array demands a single, continuous block of memory. A Linked List scatters its nodes in non-contiguous memory locations and links them together using pointers.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                In a single, perfectly continuous block of memory.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                In non-contiguous memory locations, connected by pointers.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It stores data directly inside the CPU cache for faster access.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It doesn't use memory; it writes directly to the hard drive.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In a Singly Linked List, what does every Node contain?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        A Singly Linked List only goes in one direction.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        A Singly Linked List node contains exactly two things: the actual Data, and a single "Next" pointer pointing to the next node in the chain.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Only Data
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Data, a Next pointer, and a Previous pointer
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Data and a Next pointer
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                An array of pointers
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the Time Complexity of inserting a new node at the very Front (Head) of a Linked List?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about whether you need to shift any other elements when adding to the front.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Unlike arrays, you do not have to shift any elements. You simply rewire the `next` pointer of the new node and update the `head`. This happens instantly in O(1) time.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(\log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **When traversing a Singly Linked List, how do you know you have reached the very end?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        What does the `next` pointer of the last node point to?
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The last node (the tail) has nothing to point to, so its `next` pointer is always set to `nullptr` (or `NULL`).
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The `next` pointer points back to the Head.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The `next` pointer is equal to the node's own memory address.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The `next` pointer points to `nullptr` (or `NULL`).
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The `data` value becomes $0$.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the primary advantage of a Doubly Linked List over a Singly Linked List?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        A Doubly Linked List upgrades every node to hold three things instead of two.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Because every node has a `prev` pointer, you can easily traverse the list backward from the tail, and deleting a node when you only have its pointer is incredibly fast!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It uses less memory than a Singly Linked List.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It allows you to traverse both forward and backward.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It allows for instant $O(1)$ searching of a specific element value.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It stores data in continuous memory for faster CPU caching.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In a Singly Linked List, if you want to delete the Tail (the very last node), what is the Time Complexity?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        To safely delete the tail, you need to update the node *right before* it. How do you reach that node?
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        In a Singly Linked List, you cannot step backward. To delete the tail, you must traverse all the way from the head to find the second-to-last node so you can update its `next` pointer to `nullptr`. This takes $O(N)$ time.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(\log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N^2)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you maintain a `tail` pointer in a Doubly Linked List, what is the Time Complexity of deleting the Tail?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Since it is a Doubly Linked List, the tail has a `prev` pointer!
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Because the tail has a `prev` pointer, you can instantly grab the second-to-last node (`tail->prev`), update its next pointer to `nullptr`, and delete the tail in $O(1)$ time!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(1)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                $O(\log N)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It is impossible to delete the tail in a Doubly Linked List.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the one major disadvantage of using a Doubly Linked List compared to a Singly Linked List?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about what happens when you add a `prev` pointer to every single node.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Every single node must now store an additional `prev` pointer. This means a Doubly Linked List inherently uses more memory to store the exact same amount of data as a Singly Linked List.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It is slower to insert at the Head.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It takes up slightly more memory due to the extra pointers.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It cannot be traversed forward.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                You have to shift elements when inserting.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Under the hood, the C++ STL `std::list` is implemented as which data structure?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        `std::list` allows you to instantly push and pop from both the front and the back.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `std::list` is a built-in implementation of a Doubly Linked List. This is why it supports `push_front()`, `push_back()`, and bidirectional traversal!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Singly Linked List
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Dynamic Array
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Fixed-size Array
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Doubly Linked List
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you want the absolute most memory-efficient linked list in C++ (and only need to traverse forward), which STL container should you use?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about the single-pointer alternative to `std::list`.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `std::forward_list` is the highly memory-efficient Singly Linked List implementation in C++. It uses only a single `next` pointer, saving space when bidirectional traversal isn't needed!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `std::vector`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `std::list`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `std::forward_list`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `std::stack`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Linked List, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>