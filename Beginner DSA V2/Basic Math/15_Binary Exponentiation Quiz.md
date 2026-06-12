<READING_WIDGET>
# Binary Exponentiation Quiz

Choose the correct answer for each question.
</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What is the main advantage of Binary Exponentiation (Exponentiation by Squaring) over a standard naive `for` loop?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        By continuously squaring the base and halving the exponent, Binary Exponentiation allows us to calculate massive powers in just $O(\log b)$ steps instead of $O(b)$ linear steps.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It completely prevents integer overflow
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It reduces the Time Complexity from $O(b)$ down to lightning-fast $O(\log b)$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It allows you to calculate numbers infinitely large
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It reduces the Space Complexity to zero
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Binary Exponentiation, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In the recursive approach to calculate $a^b$, what do we do mathematically when the current exponent $b$ is an ODD number?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Because integer division rounds down (e.g., $13 / 2 = 6$), we mathematically lose one power of $a$. To compensate when $b$ is odd, we square the half-power and multiply it by that extra $a$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                We return $1$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                We divide $a$ by $2$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                We square the answer of $a^{b/2}$ and multiply it by an extra $a$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                We add $a$ to the total sum
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Binary Exponentiation, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Look at the following recursive function. Why is this implementation a terrible idea that completely defeats the purpose of Binary Exponentiation?

```cpp
long long badPower(long long a, long long b) {
    if (b == 0) return 1;
    if (b % 2 == 0) {
        return badPower(a, b / 2) * badPower(a, b / 2);
    } else {
        return a * badPower(a, b / 2) * badPower(a, b / 2);
    }
}
```**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Making two identical recursive calls branches the execution tree. Instead of going straight down in $O(\log b)$ steps, the function splits into two, then four, then eight calls, ultimately resulting in an $O(b)$ time complexity. Always store the recursive call in a variable!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                It causes a syntax error because you cannot multiply recursive calls directly
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It makes the exact same recursive call twice on every step, completely destroying the $O(\log b)$ optimization and turning it back into an $O(b)$ time complexity disaster
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will infinitely loop because $b$ never reaches $0$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It will always return $0$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Binary Exponentiation, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **In the optimal Iterative algorithm, competitive programmers often use bitwise operators for speed and cleanliness. What are the exact bitwise equivalents of checking if `b` is odd (`b % 2 != 0`) and dividing `b` by 2 (`b = b / 2`)?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The bitwise AND operator (`b & 1`) checks if the very last bit is a $1$, which perfectly identifies odd numbers. The right shift operator (`b >>= 1`) shifts all bits to the right by one position, which is the exact CPU-level equivalent of dividing by $2$.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `b | 1` and `b << 1`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `b ^ 2` and `b >> 2`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `b & 1` and `b >>= 1`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `~b` and `b / 2`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Binary Exponentiation, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **You are solving a problem that passes a negative exponent as a 32-bit signed integer (`int b = -2147483648`). If you try to make it positive by simply writing `b = -b;`, what disaster occurs?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        This is the notorious `INT_MIN` trap! The absolute value of the 32-bit `INT_MIN` is strictly one unit larger than `INT_MAX`. Attempting to negate it directly causes an overflow. You must cast it to a 64-bit `long long` before negating it.
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The compiler will convert it to a `float` automatically
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                It evaluates to exactly $0$
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number exceeds the maximum 32-bit positive limit (`2147483647`) and causes an integer overflow, leaving the number negative
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The program safely continues and computes the correct answer
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Binary Exponentiation, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>
