<READING_WIDGET>
# Input, Output, and Online Judge Quiz
</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which operator is used with `cin` to take input?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about the visual flow of data. Data goes "into" your variables.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The `>>` operator is the Extraction Operator. It visually shows data flowing from the input stream (`cin`) into your variables.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `<<` (Insertion Operator)
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `>>` (Extraction Operator)
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `||`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `::`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Input, cin
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If the user types `10 20` separated by a space, how do you read both numbers into variables `a` and `b`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        You can chain the input operators directly on a single line.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `cin >> a >> b;` gracefully chains the extraction operators. C++ will automatically skip the space between the numbers and assign 10 to `a` and 20 to `b`.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin >> a, b;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin >> a >> b;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin(a, b);`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `input >> a >> " " >> b;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Input, Variables
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Why is using `\n` preferred over `endl` in competitive programming?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        `endl` does two things: it inserts a newline and performs a hidden mechanical action that drastically slows down output.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Flushing the buffer with `endl` forces the computer to write to the console immediately, which is an incredibly slow mechanical process inside large loops and causes Time Limit Exceeded (TLE) errors.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `endl` causes memory leaks.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `\n` looks cleaner in the code.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `endl` flushes the output buffer every single time, which is extremely slow and can cause Time Limit Exceeded (TLE).
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `\n` works on both Windows and Mac, while `endl` only works on Linux.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Output, Performance, endl
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the magic incantation added at the start of `main()` to massively speed up Input/Output operations?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        It involves un-syncing the standard C and C++ streams and untying input from output.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `ios_base::sync_with_stdio(false); cin.tie(NULL);` lines up two optimizations: it un-syncs C and C++ streams so they don't block each other, and it unties `cin` from `cout` so the output buffer isn't flushed every time you ask for input.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `#pragma GCC optimize("O3")`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `ios_base::fast_io();`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `ios_base::sync_with_stdio(false); cin.tie(NULL);`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin.speed(MAX);`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, CP Tricks, Fast I/O
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you want to print a `double` variable exactly up to 5 decimal places, which library must you include to use `setprecision()`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        The library's name stands for Input/Output Manipulators.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `<iomanip>` stands for Input/Output Manipulators and contains the `setprecision()` function used to explicitly format floats and doubles.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `<iostream>`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `<math.h>`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `<iomanip>`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `<precision>`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Formatting, Libraries
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **An Online Judge gives you a "Wrong Answer (WA)" verdict. What does this mean?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        It doesn't mean it crashed or took too long, it just means the logic or output format was slightly off.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        WA means your code completely successfully compiled and finished running within the time limit, but the output it generated did not perfectly match the judge's expected output.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Your program crashed.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Your program ran out of time.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Your program compiled and ran, but the output did not exactly match the expected output.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                You forgot to include a specific library.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Online Judge, Verdicts, WA
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you need to print a massive 2D matrix of 100,000 numbers, which combination of fast I/O practices is the absolute most efficient?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        You need to decouple input from output and avoid flushing the buffer.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Combining the fast I/O boilerplate (`cin.tie(NULL)`) with `\n` instead of `endl` guarantees that a massive data dump like a 100,000-element matrix won't bottleneck your program's execution time due to buffer flushing.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin >> matrix[i][j]`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cout` and `endl`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin.tie(NULL)` with `cout` and `\n`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cout` and `flush`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, CP Tricks, Fast I/O
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does `ios_base::sync_with_stdio(false);` actually do under the hood?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        C++ is backwards-compatible with C, but maintaining that compatibility is a heavy performance burden.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        By default, C++ keeps its streams synced with standard C streams so you can mix `cout` and `printf`. Disabling this sync completely removes this heavy synchronization overhead, significantly boosting speed.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It disables multi-threading.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It unsynchronizes C++ streams (`cin`/`cout`) from C streams (`scanf`/`printf`), skipping the safety checks and boosting speed.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It forces the output buffer to flush instantly.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It prevents the program from crashing if the user types a string instead of an int.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Streams, Internal Mechanics
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is a "Hidden Test Case" on an Online Judge?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        It prevents you from "cheating" by just printing out the answers to the sample inputs.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Hidden test cases are the true test of your logic's robustness. They ensure your program genuinely solves the problem for all bounds, edge cases, and scales, rather than just handling the 2 or 3 examples provided.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                A test case that crashes the judge's servers.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                A test case that tests your code against completely unseen inputs to verify it isn't just hardcoded to pass the examples.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                A test case that doesn't count towards your final score.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                A test case written in a different programming language.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Online Judge, Testing
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If an Online Judge gives you a "Time Limit Exceeded (TLE)" verdict, what is the most likely culprit?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think about nested loops and Big O notation.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        TLE means your logic took too long to run. You most likely wrote an $O(N^2)$ algorithm when an $O(N)$ one was expected, or you accidentally created an infinite `while` loop that never terminates.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                You forgot a semicolon.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Your program printed the wrong answer.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Your algorithm has an inefficient Time Complexity (e.g., $O(N^2)$ when $O(N)$ was expected) or you have an infinite loop.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                You tried to read an array out of bounds.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        Online Judge, Verdicts, TLE, Time Complexity
    </MCQ_TAGS>
</MCQ_WIDGET>
