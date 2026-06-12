<READING_WIDGET>
# Conditional Statements Quiz

Test your understanding of branching logic and decision-making in C++!

</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which operator is used to check if two values are EXACTLY equal?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `=` assigns a value, `==` compares them
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `=`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `==`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `===`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `!=`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In a sequence of `if ... else if ... else`, how many blocks of code will be executed if multiple conditions are technically true?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        An `if-else` ladder guarantees that *only* the first true block is executed, entirely skipping the rest
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                All of them.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Only the first one that evaluates to true.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Only the last one that evaluates to true.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will cause a compilation error.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **You need to check if a number `x` is between 10 and 20 (inclusive). Which is the correct syntax?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Chaining operators like `10 <= x <= 20` is syntactically legal but a massive logical trap in C++. C++ will evaluate `10 <= x` first into a `0` or `1`, and then check if that `0` or `1` is `<= 20`, which is always true! You must explicitly separate the conditions using the logical AND `&&` operator
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (10 <= x <= 20)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (x >= 10 and 20)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (x >= 10 && x <= 20)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (x >= 10 || x <= 20)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does the Logical NOT operator `!` do?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `!` simply reverses the boolean value. `!true` is `false`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It subtracts 1 from a variable.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It flips `true` to `false`, and `false` to `true`.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It checks if a variable is empty.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It ends the program immediately.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is "Short-Circuiting" in C++?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        For example, in `A && B`, if `A` is false, C++ knows the whole expression is false and completely skips evaluating `B`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                When an infinite loop crashes the program.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                When the program skips the second half of an `&&` or `||` check because the overall result is already determined by the first half.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                When `if` statements are nested too deeply.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                A compilation error caused by missing curly braces.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In a `switch` statement, what happens if you forget to put a `break;` at the end of a `case`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Fall-through is a notorious bug. Always remember your `break;` statements in a switch!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The switch statement fails to compile.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It gracefully exits the switch block automatically.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                "Fall-through" occurs: it will continue executing the code in the subsequent cases until it hits a `break` or the switch ends.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It causes an infinite loop.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the equivalent Ternary Operator for the following logic:**
        ```cpp
        int max_val;
        if (a > b) max_val = a;
        else max_val = b;
        ```
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The ternary format is `condition ? true_value : false_value;`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int max_val = a > b ? a : b;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int max_val = a > b : a ? b;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int max_val = (a > b) == a || b;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int max_val = ? a > b : a : b;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the scope of a variable declared inside an `if` block?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Variables declared inside curly braces `{}` are strictly local to that block
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It is accessible anywhere in the program.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It is accessible anywhere within the `main()` function.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It is destroyed as soon as the `if` block ends and cannot be accessed outside.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It overwrites any global variables automatically.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which of the following conditional checks will fail to compile?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `=>` is not a valid C++ operator. The greater-than-or-equal operator is strictly `>=`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (a == 5 || b == 10)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (a == 5 && b == 10)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (a => 5)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `if (a >= 5)`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you have an `if` statement without curly braces `{}`, how many lines of code belong to that `if` statement?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Omitting curly braces makes only the single next statement part of the `if`. This is a common source of bugs!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                All indented lines directly below it.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Exactly 1 line (the very next statement).
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Until a blank line is reached.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will cause a compilation error.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Conditional Statements, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>
