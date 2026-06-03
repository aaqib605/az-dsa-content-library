---
title: "Counting Principles Quiz"
slug: "quiz-counting-principles"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Test your grasp on the Addition and Multiplication principles with constraint-based combinatorial puzzles!"
---

# Counting Principles Quiz

Choose the correct answer for each question. Use the Golden Rule of Counting (AND = Multiply, OR = Add) to solve these!

## Questions

### 1. In a class, there are 15 boys and 10 girls. How many ways can a teacher select exactly 1 boy and 1 girl to represent the class at a seminar?
A. `120`  
B. `130`  
C. `150`  
D. `180`  

### 2. If $x < 4 < y$ and $x, y \in \{1, 2, 3, \dots, 10\}$, find the number of valid ordered pairs $(x, y)$.
A. `12`  
B. `15`  
C. `18`  
D. `20`  

### 3. Poor Dolly's TV has exactly 4 channels. She switches the channel every minute. How many ways can she be back to her original channel for the *very first time* exactly after 4 minutes?
A. `10`  
B. `12`  
C. `15`  
D. `18`  

### 4. Find the total number of possible subsets for a mathematical set containing $n$ elements.
A. $2^n$  
B. $n^2$  
C. $n!$  
D. $3^n$  

### 5. In how many ways can 10 distinct balls be put into 2 different boxes?
A. `512`  
B. `1024`  
C. `2048`  
D. `4096`  

### 6. A gentleman wants to invite 6 friends to a party. How many ways can he send invitation cards to them if there are exactly 3 messengers available?
A. `243`  
B. `729`  
C. `2187`  
D. `59049`  

### 7. Find the number of 4-digit numbers that can be formed if repetition of digits is **not** allowed.
A. `3024`  
B. `4536`  
C. `5040`  
D. `6048`  

### 8. Find the number of 3-digit numbers that are completely divisible by 5, assuming all digits must be distinct.
A. `108`  
B. `124`  
C. `136`  
D. `144`  

### 9. Find the number of 4-digit numbers in which **at least one** digit is repeated.
A. `4464`  
B. `5464`  
C. `6454`  
D. `6444`  

### 10. A standard 6-sided die is rolled $n$ times. What is the number of possible outcomes for the following three constraints respectively?
*(1) 6 never appears, (2) 6 appears at least once, (3) Only even numbers appear*
A. $6^n, 6^n-5^n, 3^n$  
B. $5^n, 6^n-5^n, 3^n$  
C. $5^n, 6^n+5^n, 4^n$  
D. $4^n, 5^n-6^n, 2^n$  

---

## Answer Key

1. **C** - The teacher must choose a boy **AND** a girl. By the Multiplication Principle: $15 \times 10 = 150$.
2. **C** - Since $x < 4$, $x$ can be $\{1, 2, 3\}$ (3 choices). Since $y > 4$ and bounded by 10, $y$ can be $\{5, 6, 7, 8, 9, 10\}$ (6 choices). $3 \times 6 = 18$ valid pairs.
3. **B** - Let's say she starts at Channel A. 
   - Min 1: She can switch to B, C, or D (**3 choices**). 
   - Min 2: She cannot switch to A (must wait for 4 mins) and cannot stay on the current channel (**2 choices**). 
   - Min 3: Same logic, cannot switch to A and cannot stay on current (**2 choices**). 
   - Min 4: She *must* switch back to A (**1 choice**). 
   Total paths: $3 \times 2 \times 2 \times 1 = 12$.
4. **A** - For every element in the set, you have exactly 2 choices: either **include** it in the subset, or **exclude** it. Since there are $n$ independent elements, we multiply $2 \times 2 \times 2 \dots = 2^n$.
5. **B** - Do not confuse the base and exponent! Each of the 10 independent balls has exactly 2 choices (Box 1 or Box 2). We make this choice 10 times: $2 \times 2 \times \dots = 2^{10} = 1024$.
6. **B** - Just like the balls and boxes, the friends are the ones making independent choices! Friend 1 can be sent their card via Messenger A, B, or C (3 choices). Friend 2 has 3 choices, etc. Thus, it is $3^6 = 729$.
7. **B** - A 4-digit number cannot start with 0. 
   - 1st digit: 1-9 (**9 choices**). 
   - 2nd digit: Any digit except the first (**9 choices**). 
   - 3rd digit: Any digit except the first two (**8 choices**). 
   - 4th digit: **7 choices**. 
   $9 \times 9 \times 8 \times 7 = 4536$.
8. **C** - To be divisible by 5, the number must end in 0 **OR** 5. This requires the Addition Principle to split into two independent cases!
   - *Case 1 (Ends in 0):* 3rd digit is 0 (1 choice). 1st digit has 9 choices (1-9). 2nd digit has 8 choices. $9 \times 8 \times 1 = 72$.
   - *Case 2 (Ends in 5):* 3rd digit is 5 (1 choice). 1st digit cannot be 0 or 5 (8 choices). 2nd digit cannot be 5 or the 1st digit (8 choices). $8 \times 8 \times 1 = 64$.
   Total: $72 + 64 = 136$.
9. **A** - A classic combinatorics trick! `Total Valid Outcomes = Total Possible Outcomes - Invalid Outcomes`. 
   The total number of 4-digit numbers is $9 \times 10 \times 10 \times 10 = 9000$. 
   The total number of 4-digit numbers with *no* repetition (invalid outcomes for this question) is 4536 (from Question 7). 
   Thus, numbers with at least one repetition = $9000 - 4536 = 4464$.
10. **B** - 
    - *Constraint 1:* If 6 never appears, each roll only has 5 valid faces (1-5). Result: $5^n$.
    - *Constraint 2:* Using the Total-None trick, `At least one 6` = `Total Outcomes` ($6^n$) - `Outcomes with no 6s` ($5^n$). Result: $6^n - 5^n$.
    - *Constraint 3:* If only evens appear, each roll has 3 valid faces (2, 4, 6). Result: $3^n$.
