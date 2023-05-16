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

**Fermat's Little Theorem:** Suppose that $$p$$ is prime and $$a$$ is an integer not divisible by $$p$$.  Then $$a^{p-1}\equiv 1\mod p$$.

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

## Pseudoprimes

More than $$25$$ centuries ago, Chinese mathematicians came up with an interesting conjecture for checking whether a number is prime.

**Ancient conjecture:** An integer $$n>1$$ is prime if and only if $$n \mid 2^n-2$$.

Notably, Fermat's Little Theorem, says that one direction is definitely true: if $$p$$ is prime, then $$2^p=2\mod p$$ and therefore $$p\mid 2^n-2$$.
Unfortunately, the other direction is not true and gives rise to the notion of pseudoprimes.

**Definition:** A composite integer $$n$$ is called a **pseudoprime** if $$n\mid 2^n-2$$.  More generally, we say $$n$$ is called **pseudoprime to base** $$a$$ if $$n\mid a^n-a$$.  If $$n$$ is pseudoprime to every base, it is called an **absolute pseudoprime** or, as mentioned above, a **Charmichael number**.

Ancient mathematicians had good reasons for believeing that $$n\mid 2^n-2$$ was a plausible conjecture.  It works for all integers $$n\leq 340$$.
The first time that it fails is for the number $$341$$.

**Example:** $$341 = 11\cdot 31$$, even though $$341\mid 2^{341}-2$$.

Unlike with prime numbers, we can easily write down a recursive formula for obtaining larger and larger pseudoprimes.

**Theorem:**

Suppose that $$n$$ is a pseudoprime.  Then $$2^n-1$$ is also a pseudoprime.

**Proof:**

Since $$n$$ is a pseudoprime, we know that $$n$$ is composite.
As we have already seen, if $$n$$ is composite, then $$2^n-1$$ is composite.
Furthermore since $$n \mid 2^n-2$$, we know that $$2^{n-2} = nk$$ for some integer $$k$$.  Therefore

$$2^{2^n-1}-2 = 2(2^{2^n-2}-1)=2(2^{nk}-1) = 2(2^n-1)(1 + 2^{n} + 2^{2n} + \dots + 2^{(k-1)n}).$$

It follows that $$2^n-1$$ divides $$2^{2^n-1}-2$$ and therefore $$2^n-1$$ is a pseudoprime.
:black_square_button:

Thus

$$341,\ \ 2^{341}-1,\ \ 2^{2^{341}-1}-1,\dots$$

defines an infinite sequence of pseudoprimes.

Despite our ability to construct arbitrarily large pseudoprimes, they actually seem to be quite rare in comparison to primes.
* Most numbers $$n$$ satisfying $$n\mid 2^n-1$$ turn out to be prime.  Therefore pseudoprimes are much rarer than primes.
* In fact, there are only $$247$$ smaller than a million, compared to the $$78498$$ primes.

Absolute pseudoprimes, ie. Charmichael numbers, are even rarer.
To produce a Charmichael number, we can use the condition established by the following theorem.

**Theorem:** Suppose that $$n=p_1p_2\dots p_r$$ for some *distinct* primes $$p_1,\dots, p_r$$ (this is called being square-free).  If $$p_i-1 \mid n-1$$ for all $$i$$, then $$n$$ is a Charmichael number.

**Proof:** Let $$a\in\mathbb Z$$.  We need to show that $$a^n=a\mod n$$, ie. that $$n\mid a^n-a$$.  Since all of the primes are distinct, it suffices to show that $$p_i\mid a^n-a$$ for all $$i$$.

By assumption, we know that $$n-1 = (p_i-1)k$$.
Therefore

$$a^n-a = a(a^{n-1}-1) = a(a^{(p_i-1)k}-1) = (a^{p_i}-a)(1 + a^{p_i-1} + a^{2(p_i-1)} + \dots + a^{(k-1)(p_i-1)}).$$

By Fermat's Little Theorem, $$p_i$$ divides $$a^{p_i}-a$$ and so the above factorization shows $$p_i$$ divides $$a^n-a$$.

:black_square_button:

**Example:** $$7\cdot 13\cdot 19 = 1729$$ is a Charmichael number.



