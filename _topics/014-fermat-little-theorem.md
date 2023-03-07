---
layout: page
title: Fermat's Little Theorem
---


Suppose that $$p$$ is a prime number and $$a$$ is some other number not divisible by $$p$$.
What happens to the value of $$a^k\mod p$$ as $$k$$ increases?

In terms of remainders, we have limited options, namely $$0,1,\dots, p-1$$.
Therefore at some point, we will need to repeat a residue, ie. there will be positive integers $$0 < j < k$$ with $$a^j\equiv a^k\mod p$$.
Since $$a^j$$ and $$p$$ are relatively prime, we can divide both sides by $$a^j$$, getting $$1\equiv a^{k-j}\mod p$$.
To summarize, $$a^m\equiv 1\mod p$$ for some positive integer $$m$$.
Fermat's Little Theorem tells us what the integer is.

**Fermat's Little Theorem:** Suppose that $$p$$ is prime and $$a$$ is an integer not divisible by $$p$$.  Then $$a^{p-1}\equiv a\mod p$$.

**Proof:**

Consider the values

$$a,\ 2a,\ 3a\ 4a\ \dots\ (p-1)a.$$

None of these values are equivalent to $$0\mod p$$ since none of them are divisible by $$p$$.
Furthermore, none of them are congruent modulo $$p$$, since if they were, then we would have $$ja\equiv ka\mod p$$ for some $$1\leq j < k\leq p-1$$, meaning $$(k-j)a$$ would be divisible by $$p$$, a contradiction.
Thus by the Pidgeonhole Principle, the remainders of $$a,2a,3a,\dots, (p-1)a$$ are $$1,2,\dots, p-1$$ all in some order.
Hence the product 

$$a\cdot 2a\cdot 3a\cdot\dots\cdot (p-1)a\equiv 1\cdot 2\cdot 3\cdot \dots\cdot (p-1)\mod p.$$

This simplifies to $$a^{p-1}(p-1)!\equiv (p-1)!\mod p$$.
Since $$p$$ and $$(p-1)!$$ are relatively prime, we can divide both sides by $$(p-1)!$$, getting $$a^{p-1}\equiv 1\mod p$$.
:black_square_button:

One nice corollary of Fermat's Little Theorem is th following.

**Corollary:** Let $$p$$ be prime.  Then for any integer $$a$$, $$a^p\equiv a\mod p$$.

**Proof:**

If $$a$$ is divisible by $$p$$, then both sides are equivalent to $$0\mod p$$.  Otherwise, Fermat's Little Theorem applies and we have $$a^{p-1}\equiv 1\mod p$$ and mulitpliying both sides by $$a$$ proves our theorem.
:black_square_button:


Fermat's Little Theorem has many applications in number theory, from basic calculations to important theoretical results.

**Problem:** Determine the positive remainder obtained by dividing $$5^{2023}$$ by  $$11$$.

**Solution:** By Fermat's Little Theorem, $$5^{10}\equiv 1\mod 11$$.  Therefore We can write $$5^{2023} = 5^3\cdot (5^{10})^{202}\equiv 5^3\mod 11 = 4\mod 11$$.
:black_square_button:

As a theoreical application of Fermat's Little Theorem, we have an interesting test for whether a number is prime.

**Fermat Primality Test:**  If we can find an integer $$a$$ with $$a^p\not\equiv a\mod p$$, then $$p$$ is not prime.

**Example:**  Let's try to determine whether $$203$$ is prime.

We will use the binary exponent algorithm to get

$$3^{203} = 3^{2^0}3^{2^1}3^{2^3}3^{2^6}3^{2^7}.$$

The relevant powers of $$3$$ ar calculated to be 

| $$k$$ | $$3^{2^k}\mod 203$$ |
| ----- | ------------------- |
|   0   |      3  |
|   1   |      9  |
|   2   |     81  |
|   3   |     65  |
|   4   |    165  |
|   5   |     23  |
|   6   |    123  |
|   7   |    107  |

Therefore

$$3^{203}\equiv 3\cdot 9\cdot 65\cdot 123\cdot 107\mod 203 \equiv 12\mod 203.$$

Therefore $$203$$ is not prime.  In fact, $$203 = 7\cdot 29$$.

:warning: **The converse is false!** : If $$a^n\equiv a$$ for all integers $$a$$, it still may not be true that $$a$$ is prime.  Therefore Fermat's Primality Test gives a necessary but insufficient condition for primality.

**Definition:** A composite number $$n$$ satisfying $$a^n\equiv a$$ for all integers $$a$$ is called a **Charmichael number**.

**Example:** The number $$561$$ is a Charmichael number.



