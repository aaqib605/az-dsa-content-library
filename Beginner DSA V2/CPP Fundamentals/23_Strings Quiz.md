<READING_WIDGET>
# Strings Quiz

Test your understanding of C++ Strings and Character manipulation!

</READING_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If a user types `John Doe` into the console, and you read it using `cin >> s;`, what will the string `s` contain?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Standard `cin >>` stops reading the moment it hits any whitespace. It will only capture "John"
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `"John Doe"`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `"John"`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `"Doe"`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                A compilation error
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **How do you correctly read an entire line of text, including the spaces, into a string `s`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `getline(cin, s)` reads the entire stream until the user hits the Enter key. **Warning:** If you use `cin >>` right before `getline`, it leaves a newline `\n` in the buffer, causing `getline` to instantly read an empty string! Use `cin.ignore()` to clear it
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin.read(s);`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `cin >> s >> spaces;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `getline(cin, s);`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `scanf(s);`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which operator is used to concatenate (join) two strings together in C++?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        The `+` operator smoothly concatenates strings, e.g., `"Hello" + " World"`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `.`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `&`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `+`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `||`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Are strings in C++ mutable (modifiable)?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Unlike Java or Python, C++ strings are mutable. You can directly edit `s[i]` without creating a whole new string!
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Yes, you can change individual characters directly (e.g., `s[0] = 'Z'`).
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                No, strings are completely immutable like in Python or Java.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Only if you use a special library.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Yes, but only for lowercase letters.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **If you have `char ch = '5';`, what is a clever way to convert it into the actual integer `5` using ASCII math?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Since `'0'` has an ASCII value of 48, subtracting `'0'` from any character digit gives you its actual integer value. Writing `ch - '0'` is standard CP practice because it is much more readable than hardcoding 48
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int val = ch - '0';`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int val = to_int(ch);`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int val = ch / 10;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `int val = (int)ch;`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does the `.length()` or `.size()` method return for a string?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        It simply returns the character count, operating in $O(1)$ time
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number of bytes the string occupies in memory.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number of characters currently inside the string.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The maximum capacity of the string.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The number of vowels in the string.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does the `#include <string>` library provide that standard C character arrays do not?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        C++ strings handle their own memory, freeing you from dealing with `char[]` limits and null terminators
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                Faster execution times.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Built-in dynamic resizing, easy assignment, and concatenation.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                The ability to store numbers.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Nothing, they are exactly the same.
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **How do you append a single character `'A'` to the end of a string `s`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        Both `push_back()` and `+=` are highly efficient ways to append characters in $O(1)$ time
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `s.add('A');`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `s.push_back('A');`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `s += 'A';`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                Both B and C work!
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **Which method is used to extract a portion (substring) of a string?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `s.substr(start_index, length)` is the standard way to grab substrings
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `s.slice()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `s.substr()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `s.split()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `s.cut()`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>

<MCQ_WIDGET>
    <MCQ_DESCRIPTION>
        **What does `s.find("apple")` return if the word "apple" is NOT found inside the string `s`?**
    </MCQ_DESCRIPTION>
    <MCQ_HINT>
        Think critically about the concepts discussed in this module.
    </MCQ_HINT>
    <MCQ_EXPLANATION>
        `string::npos` represents "no position" and is typically the maximum possible value for `size_t`
    </MCQ_EXPLANATION>
    <MCQ_OPTIONS>
        <OPTION_ITEM>
            <OPTION_BODY>
                `-1`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `false`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `0`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>0</OPTION_IS_CORRECT>
        </OPTION_ITEM>
        <OPTION_ITEM>
            <OPTION_BODY>
                `string::npos`
            </OPTION_BODY>
            <OPTION_IS_CORRECT>1</OPTION_IS_CORRECT>
        </OPTION_ITEM>
    </MCQ_OPTIONS>
    <MCQ_TAGS>
        C++, Strings, Quiz
    </MCQ_TAGS>
</MCQ_WIDGET>
