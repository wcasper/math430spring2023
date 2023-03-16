---
layout: page
title: Practice Exam 2 Solution
permalink: /exams/practice-exam2-soln
---

Solve each of the following problems.
If the problem asks for a proof, be sure to carefully justify your work, including any theorems from class.

Note: you may NOT use a theorem or result from class to prove something when it makes the problem entirely trivial.  If you are unsure whether a particular theorem or result is allowed, just ask!

## Problem 1 (True or False)
For each of the following, write TRUE if the statement is true and FALSE if the statement is false.  NO explanation is needed.

a) If $$n$$ divides $$2^n-2$$, then $$n$$ is prime

**False.** Composite numbers with this property are called pseudoprimes.

b) If $$14\mid a^2$$ then $$14\mid a$$

**True.** We get $$2\mid a^2$$ and since $$2$$ is prime, $$2\mid a$$.  Likewise $$7\mid a$$ and therefore $$14\mid a$$.

c) Any number is equivalent modulo $$8$$ to one of the numbers in $$\{-3,-2,-1,0,1,2,3,4\}$$

**True.** Just subtract the possible positive remainders by $$3$$.

d) Chebyshev's estimate says that there are at least $$n\log(2)/\log(2n)$$ primes less than $$2n$$

**True.**

e) The number $$1434_7$$ is divisible by $$6$$.

**True.** The number is $$4+3\cdot 7 + 4\cdot 7^2 + 1\cdot 7^3$$, which reduced modulo $$6$$ is $$12$$.


## Problem 2

a) Describe the Sieve of Eratosthenes

This is a method of determining all the prime numbers less than or equal to a fixed number $$n$$.
We start with the smallest prime, and cross out all multiples of that prime.
Iterating this process, the numbers left over which have not been crossed out are the primes.

b) State the Chinese Remainder Theorem

Let $$n_1,n_2,\dots, n_r$$ be positive integers with $$\gcd(a_j,a_k)=1$$ for $$j\neq k$$.
Then for any integers $$a_1,a_2,\dots, a_r$$, the system of linear congruences

$$\left\lbrace\begin{array}{c}
x\equiv a_1\mod n_1\\
x\equiv a_2\mod n_2\\
\vdots
x\equiv a_r\mod n_r
\end{array}\right.$$

has a solution, which is unique up to equivalence modulo $$n_1n_2\dots n_r$$.

c) Let $$a$$ and $$b$$ be integers.  Write the definition of $$a$$ being congruent to $$b$$ modulo $$n$$.

Two numbers $$a$$ and $$b$$ are congruent modulo $$n$$  if and only if $$n\mid (b-a)$$.

## Problem 3

a) Give, with justification, a nontrivial factor of $$2^{2023}-1$$.  [Hint: $$2023 = 7\cdot 17^2$$]

$$2^{2023}-1 = (2^7-1)(1 + 2^7 + 2^{14} + \dots + 2^{(17^2-1)7})$$

Therefore $$2^7-1=127$$ divides $$2^{2023}-1$$.

b) Give, with justification, a nontrivial factor of $$2^{28}+1$$.

This is similar to the factorization in (a).  We have that

$$a^n-b^n = (a-b)(a^{n-1} + a^{n-2}b + a^{n-3}b^2 + \dots + ab^{n-2}+b^{n-1}).$$

If we take $$n=7$$ and $$a = 2^4$$ and $$b=-1$$, then

$$2^{28}+1 = (2^4+1)(2^{6\cdot 4} - 2^{5\cdot 4} + 2^{4\cdot 4} - 2^{3\cdot 4} + 2^{2\cdot 4} - 2^{ 4} + 1).$$

In particular $$17$$ divides $$2^{28}+1$$.


## Problem 4

Find all solution of the following equations

a) $$23x + 14y = 200$$, with $$x,y\in\mathbb{Z}$$

We use the Euclidean algorithm to get that the gcd of $$14$$ and $$23$$ is $$1$$, and moreover that

$$5\cdot 14 - 3\cdot 23 = 1.$$

Using this, every solution of the Diophantine equation is

$$x = 200(5 + 23k),\quad\quad y = 200(-3 - 14k),\quad\quad k\in \mathbb{Z}.$$

b) $$3x\equiv 4\mod 20$$

We see that $$7\cdot 3 = 21\equiv 1\mod 20$$ and therefore

$$x\equiv 8\mod 20$$.

Therefore $$x = 8 + 20k$$ for some $$k\in\mathbb{Z}$$.

## Problem 5

a) Prove that if $$a\equiv b\mod n$$, then $$ac\equiv bc\mod n$$.

Proof: If $$n\mid b-a$$ then $$a\mid (b-a)c = bc-ac$$.

b) Prove that if $$ac\equiv bc\mod n$$ and $$\gcd(c,n) = 1$$, then $$a\equiv b\mod n$$.

Proof: We have $$(b-a)c = nk$$ for some integer $$k$$.  Now there exists $$x,y\in\mathbb{Z}$$ with $$cx+ny=1$$. Multiplying the previous equation by $$x$$ on both sides, we get $$(b-a)cx = nkx$$, which tells us

$$(b-a)(1-ny) = nkx$$

and therefore $$(b-a) = n(kx + by-ay)$$, so that $$n\mid (b-a)$$.  Thus $$a\equiv b\mod n$$.

## Problem 6

a) Find, with justification, the last three digits of $$7^{999}$$

One way to solve this is to notice that $$7^4 = 2401\equiv 401\mod 1000$$.
Therefore

$$7^{999} = 7^{3}7^{996} \equiv 7^3(401)^{249}\mod 1000.$$

Now by the Binomial Theorem,

$$(401)^{249} = (400 + 1)^{249} \equiv 1 + \binom{249}{1}400\mod 1000.$$

Consequently

$$7^{999} = 343\cdot (1 + 249\cdot400) \equiv 143\mod 1000.$$

Thus the last three digits are $$143$$.

b) Let $$p$$ be prime.  Show that if $$a^2\equiv 1\mod p$$, then $$a\equiv 1$$ or $$a\equiv -1$$.

We have that $$a^2-1\equiv 0\mod p$$ and therefore $$(a-1)(a+1)\equiv 0\mod p$$.  In other words $$p$$ divides $$(a-1)(a+1)$$.  Since $$p$$ is prime, it follows that $$a-1\equiv 0$$ or $$a+1\equiv 0$$ mod $$p$$.

## Problem 7

Find all solutions of the system of equations

$$\left\lbrace\begin{array}{c}
2x\equiv 3\mod 5\\
4x\equiv 2\mod 6\\
3x\equiv 2\mod 7
\end{array}\right.$$

satisfying the property that $$0\leq x < 210$$.

First of all $$\gcd(4,6) = 2$$ and therefore $$4x\equiv 2\mod 6$$ can be reduced to $$2x\equiv 1\mod 3$$.
Since $$2\cdot 3\equiv 1\mod 5$$ and $$-2\cdot 3\equiv 1\mod 7$$.  Using this, we can reduce the system to

$$\left\lbrace\begin{array}{c}
 x\equiv 4\mod 5\\
 x\equiv 2\mod 3\\
 x\equiv -4\mod 7
\end{array}\right.$$

The proof of the Chinese Remainder Theorem tells us to consider

$$x = a\cdot 35 + b\cdot 21 + c\cdot 15.$$

Reducing this expression mod $$3$$, we get $$2a\equiv 2\mod 3$$ or $$a\equiv 1\mod 3$$.
Similarly, we get $$b\equiv 4 \mod 5$$ and $$c\equiv -4\mod 7$$.
Therefore, up to a multiple of $$210$$, we get

$$x = 1\cdot 35 + 4\cdot 21 - 4\cdot 15 = 59.$$

This solution is unique up to equivalence mod $$7\cdot 5\cdot 3 = 105$$.
Thus we actually have **two** solutions in the desired range: $$59$$ and $$164$$.


