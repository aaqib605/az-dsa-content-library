---
title: "Modular Arithmetic Quiz"
slug: "quiz-modular-arithmetic"
track: "beginner-dsa"
level: "Beginner"
order: 1
status: "Draft"
description: "Put your modular arithmetic skills to the ultimate test with these hand-crafted edge cases, overflow traps, and FLT questions."
---

# Modular Arithmetic Quiz

Choose the correct answer for each question.

## Questions

### 1. Predict the output of the following C++ code:
```cpp
#include <iostream>
using namespace std;

int main() {
	float x = 5.25;
	float y = 2.45;
	int ans = x % y;
	cout << ans;
	return 0;
}
```
A. `0`  
B. `1`  
C. `5.25`  
D. `Compiler Error`  

### 2. Predict the output of the following C++ code:
```cpp
#include <iostream>
using namespace std;

int main() {
	int res = 2 + 3 % 4 * 6 % 2 - 9 % 10 + 10 % 5;
	cout << res;
}
```
A. `-7`  
B. `2`  
C. `5`  
D. `-2`  

### 3. If you need to subtract $B$ from $A$ modulo $M$, which of the following C++ implementations perfectly prevents the notorious "Negative Modulo Trap"?
A. `(A % M - B % M) % M`  
B. `abs(A % M - B % M) % M`  
C. `(A % M - B % M + M) % M`  
D. `(A - B) % M + M`  

### 4. Predict the output of the following C++ code involving 32-bit `int` limits:
```cpp
#include <iostream>
using namespace std;

int main() {
	int a = 2147483647; // INT_MAX
	int b = 2147483647; // INT_MAX
	
	int res1 = (a + b) % a;
	int res2 = (a - b) % a;
	
	cout << res1 << " " << res2;
}
```
A. `-2 0`  
B. `0 0`  
C. `0 -2`  
D. `Error`  

### 5. Predict the output of the following C++ code involving 64-bit `long long`:
```cpp
#include <iostream>
using namespace std;

int main() {
	long long a = 2147483647;
	long long b = 2147483647;

	int res1 = (a + b) % a;
	int res2 = (a - b) % a;
	cout << res1 << " " << res2;
}
```
A. `-2 0`  
B. `0 0`  
C. `Error`  
D. `-1 -1`  

### 6. Predict the output of this incredibly tricky code. Read carefully!
```cpp
#include <iostream>
using namespace std;

int main() {
	int a = 2147483646; // Exactly divisible by 11! (a % 11 == 0)
	int b = 2147483645; 

	int res1 = (a % 11 * b % 11) % 11;
	int res2 = (a * b) % 11;
	int res3 = (a * 1LL * b) % 11;
	int res4 = (a * b * 1LL) % 11;
	
	cout << res1 << " " << res2 << " " << res3 << " " << res4;
}
```
A. `0 0 0 0`  
B. `0 -7 0 -7`  
C. `-7 -7 -7 -7`  
D. `0 -7 0 0`  

### 7. What is the fundamental mathematical requirement for the Modular Multiplicative Inverse of $b$ modulo $m$ to exist?
A. $m$ must be a prime number  
B. $b$ and $m$ must be coprime ($\text{gcd}(b, m) = 1$)  
C. $b$ must be strictly less than $m$  
D. $b$ must be an even number  

### 8. According to Fermat's Little Theorem, if $p$ is a prime number and $b$ is an integer not divisible by $p$, what does $b^{p-2} \pmod p$ calculate?
A. The square root of $b$  
B. The modular multiplicative inverse of $b$ modulo $p$  
C. Always $0$  
D. Always $1$  

### 9. Why is $10^9 + 7$ so universally preferred as a modulus in competitive programming? (Select the most critical algorithmic reason)
A. Because it is the largest prime number known to modern mathematics  
B. Because computers natively process the number 7 faster than other digits  
C. Because its square ($\approx 10^{18}$) fits perfectly inside a 64-bit `long long` integer, preventing overflow during intermediate modular multiplication steps  
D. Because it is the only 10-digit number that can be stored in an `int`  

### 10. What is the mathematically correct remainder when $2^{20} + 11^7 + 4^{40} + 3^{30} + 5^{50}$ is divided by $7$?
*(Hint: Use Fermat's Little Theorem $a^{p-1} \equiv 1 \pmod p$ to simplify the massive exponents!)*
A. `3`  
B. `0`  
C. `6`  
D. `5`  

## Answer Key

1. D - The modulo operator (`%`) in C++ is strictly defined for integer types. Attempting to use it on `float` or `double` data types will result in a Compiler Error.
2. A - Modulo (`%`) and Multiplication (`*`) share the same precedence and are evaluated strictly Left-to-Right. `3 % 4 = 3`. `3 * 6 = 18`. `18 % 2 = 0`. Evaluating the rest leaves us with `2 + 0 - 9 + 0 = -7`.
3. C - Subtracting remainders in C++ can result in a negative number. Because C++ natively returns negative remainders for negative numbers, you must manually add the modulus $M$ before the final `% M` to physically push the result back into the positive spectrum.
4. A - `INT_MAX` is $2^{31}-1$. Adding `INT_MAX + INT_MAX` results in a massive integer overflow. In 32-bit signed two's complement arithmetic, this overflow wraps around to exactly `-2`. Therefore, `res1 = -2 % a = -2`.
5. B - By declaring `a` and `b` as 64-bit `long long` integers, the addition $(a + b)$ comfortably fits in memory without overflowing. Mathematically, $(a + a) \pmod a = 0$, so `res1` correctly evaluates to `0`.
6. B - `res1`: Safe because modulo is applied immediately (`0`). `res2`: `a * b` overflows the 32-bit `int`, wrapping around to a negative number (`-2147483642`), yielding `-7 % 11`. `res3`: The `1LL` casts `a` to a 64-bit integer *before* multiplication, preventing overflow, yielding the mathematically correct `0`. `res4`: The `1LL` is placed *after* `a * b`, meaning the 32-bit overflow already happened before the cast! Result: `-7`.
7. B - A modular inverse physically cannot exist if $b$ and $m$ share a common factor greater than $1$. Therefore, they must be perfectly coprime ($\text{gcd}(b, m) = 1$). While making $m$ prime is a great way to guarantee co-primality, it is not the *only* way.
8. B - Fermat's Little Theorem establishes that $b^{p-1} \equiv 1 \pmod p$. By splitting one $b$ away, we get $b \times b^{p-2} \equiv 1 \pmod p$. Because the definition of an inverse is a number that multiplies to $1$, $b^{p-2}$ *is* the modular multiplicative inverse!
9. C - The brilliance of $10^9+7$ is that it fits in a 32-bit integer, and multiplying two numbers modulo $10^9+7$ creates an intermediate number of at most $10^{18}$, which safely fits inside a 64-bit `long long` without overflowing.
10. A - Because $7$ is prime, Fermat's Little Theorem states $x^6 \equiv 1 \pmod 7$. Thus, we can modulo all the exponents by $6$! $2^{20} \rightarrow 2^2 \rightarrow 4$. $11^7 \rightarrow 4^1 \rightarrow 4$. $4^{40} \rightarrow 4^4 \equiv 256 \equiv 4$. $3^{30} \rightarrow 3^0 \rightarrow 1$. $5^{50} \rightarrow 5^2 \equiv 25 \equiv 4$. Sum them up: $4+4+4+1+4 = 17$. $17 \pmod 7 = 3$.
