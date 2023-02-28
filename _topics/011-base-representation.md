---
layout: page
title: Base representation
---

Integers can be represented in multiple ways by choosing a **base**.
We are most familiar with base $$10$$, where an integer like $$1232194$$ really means the same thing as

$$4\cdot 10^0 + 9\cdot 10^1 + 1\cdot 10^2 + 2\cdot 10^3 + 3\cdot 10^4 + 2\cdot 10^5 + 1\cdot 10^6.$$

**Theorem:**  Let $$b>1$$ be an integer.  Then any positive integer $$n$$ can be represented **uniquely** in the form

$$n = a_0b^0 + a_1b^1 + a_2b^2 + \dots + a_mb^m$$

for some $$m\geq 0$$ and some sequence of integers $$a_0,a_1,\dots, a_m$$ with $$0\leq a_k < b$$ for all $$k$$.

**Notation:**  We use

$$(a_ma_{m-1}a_{m-2}\dots a_2a_1a_0)_b = a_0b^0 + a_1b^1 + a_2b^2 + \dots + a_mb^m.$$

When omitted, we typically assume the base $$b = 10$$, unless stated otherwise.

**Example:**  The number $$1024$$ (in base $$10$$) is the same as $$2^{10}$$.  Therefore in base $$2$$, its the same as

$$10000000000_2$$

In base $$9$$ it is the same as $$9^3 + 3\cdot 9^2 + 5\cdot 9 + 7$$, ie

$$1357_9$$.


Expansions of numbers by different bases have lots of great applications.


## Binary Exponential Algorithm

We will often be faced with the task of calculating $$c^m\mod n$$.
Such a task can be simplified by expanding the exponent $$m$$ in **base 2**

$$m = (a_ka_{k-1}\dots a_1a_0)_2$$.

Then the value we are searching for simplifies to

$$c^m = c^{2^{a_1}}c^{2^{a_2}}\dots c^{2^{a_n}}.$$

Using the fact that modular equivalence is compatible with multiplication, this means that we can reduce our calculation to just determining the value of $$c^{2^k}}$ for various values of $$k$$ and then multiplying all the results in the end to obtain our final product.  This procedure is referred to as the **binary exponential algorithm**.

**Example:**  Suppose we wish to calculate $$5^{110}\mod 131$$.  We first write $$110 = 1101110_2$$ and then work out the values of $$5^{2^j}\mod 131$$ for $$0\leq j\leq 6$$.
The key here is that this can be done recursively by *squaring*.

| $$j$$ | $$5^{2^j}\mod 131$$ |
| ----- | ------------------- |
|   1   |  25 |
|   2   | 101 |
|   3   | 114 |
|   4   |  27 |
|   5   |  74 |
|   6   | 105 |


Thus

$$5^{110} \equiv (105)(74)(27)(114)(101)\equiv 60\mod 131.$$


:warning: **Direct computation often fails**:  If we just plugged $$5^{110}$$ into a calculator, we are going to get a crazy large number with $$76$$ digits.  Many calculators will **not** give you a value with all these digits of accuracy.  Even if it does, we are still left with the horrbile task of reducing an obnoxiously large number modulo a small one.


**Example:** Suppose we wanto find $$19^{53}\mod 503$$.
We know that $$53 = 110101_2$$, so we need powers of $$19^{2^j}$$ up to $$j=5$$.

| $$j$$ | $$19^{2^j}\mod 503$$ |
| ----- | -------------------- |
|   0   |  19 |
|   1   | 361 |
|   2   |  44 |
|   3   | 427 |
|   4   | 243 |
|   5   | 198 |

Therefore

$$19^{53}\equiv (198)(243)(44)(19)\equiv 406\mod 503.$$

## Divisibility by $$9$$ and $$11$$

As a second application, we can chech if a number is divisible by $$9$$ in a very interesting way.  To start, we need a simple theorem about divisibility of polynomials with integer coefficients.

**Theorem:**  Let $$f(x)$$ be a polynomial with integer coefficients.  If $$a\equiv b\mod n$$, then $$f(a)\equiv f(b)\mod n.$$

Using this, we can get a very famous check for the divisibility of a number by $$9$$.

**Theorem:** A number $$n$$ is divisible by $$9$$ if and only if the sum of its digits is divisible by $$9$$.

**Proof:**  Let

$$n=a_m\cdot 10^m + a_{m-1}\cdot 10^{m-1} + \dots + a_1\cdot 10 + a_0.$$

Then since $$10 \equiv 1\mod 9$$, we know that the polynomial $$f(x) = \sum_{k=0}^m a_k\cdot x^k$$ satisfies the property that $$f(1)\equiv f(10)\mod 9$$.  However, $$f(1)$$ is just the sum of the digits of $$n$$ and $$f(10)$$ is $$n$$.  Since divisibility by $$9$$ is the same as being equivalent to $$0$$ modulo $$9$$, the result follows immediately.
:black_square_button:


In fact, by repeatedly summing the digits of a number, we eventually will end up with a single-digit number called the **digital root**.  Repeated application of thee previous theorem leads to the following conclusion.

**Theorem:** A number is divisible by $$9$$ if and only if its digital root is $$9$$.

**Example:** Consider the number $$176521221$$.  The sum of its digits is $$27$$.  The sum of the digits of $$27$$ is $$9$$.  Therefore the digital root is $$9$$ and $$176521221$$ must be divisible by $$9$$.


The same strategy as we saw above also gives us a way to check for divisibility by $$11$$.
**Theorem:** A number $$n$$ is divisible by $$11$$ if and only if the *alternating* sum of its digits is divisible by $$11$$.

**Proof:**

Let

$$n=a_m\cdot 10^m + a_{m-1}\cdot 10^{m-1} + \dots + a_1\cdot 10 + a_0.$$

Then since $$10 \equiv -1\mod 11$$, we know that the polynomial $$f(x) = \sum_{k=0}^m a_k\cdot x^k$$ satisfies the property that $$f(-1)\equiv f(10)\mod 9$$.  However, $$f(-1)$$ is the alternating sum

$$a_0 - a_1 + a_2 - a_3 + \dots + (-1)^ma_m$$

and $$f(10) = n$$.  The result follows immediately.

:black_square_button:

These results can also be extended to expansions via other bases.  The proof is similar.

**Theorem:**  A number is divisible by $$b+1$$ if and only if the sum of its digits base $$b$$ is divisible by $$b+1$$.







