---
layout: page
title: Sieve of Eratosthenes
---

The notion of congruence of integers was defined by Gauss to study the behavior of remainders.

**Definition:** Two integers $$a$$ and $$b$$ are said to be **congruent modulo** $$n$$ if $$a-b$$ is divisible by $$n$$. In this case, we write

$$a\equiv b\mod n$$.


## Properties of modular equivalence

It is easy to see that
 * (reflexivity): $$a\equiv a\mod n$$
 * (symmetry): $$a\equiv b\mod n$$ if and only if $$b\equiv a\mod n$$
 * (transitivity): $$a\equiv b\mod n$$ and $$b\equiv c\mod n$$ implies $$a\equiv c\mod n$$.

Thus, equivalence modulo $$n$$ defines an **equivalence relation**.

Even more interestingly, one can prove that equivalence modulo $$n$$ is compatible with the usual algebraic operations.
* (additivity): $$a\equiv b\mod n$$ and $$c\equiv d\mod n$$ implies $$(a+c)\equiv (b+d)\mod n$$.
* (multiplicativity): $$a\equiv b\mod n$$ and $$c\equiv d\mod n$$ implies $$ac\equiv bd\mod n$$.

In particular, these two identities imply that if $$a\equiv b\mod n$$ then

$$ac\equiv bc\mod n,\quad a+c\equiv b+c\mod n,\quad a^k=b^k\mod n.$$

These have many great applications in the world of numbers, as the following examples show.

**Example Problem:**  Show that $$41$$ divides $$2^{20}-1$$.

**Solution:**  Equivalently, we must show that $$2^{20}\equv 1\mod 41$$.
We can see $$2^5 = 32 \equiv -9\mod 41$$.  Therefore

$$2^{20} = (2^5)^4 \equiv (-9)^4\mod 41.$$

Then since $$(-9)^2= 81\equiv -1\mod 41$$, we find that

$$(-9)^4 = ((-9)^2)^2\equiv (-1)^2\mod 41.$$

We conclude that $$2^{20}\equiv 1\mod 41$$.
:black_square_button:

**Example Problem:**  Show that for any $$n\geq 1$$, $$7$$ divides $$5^{2n}+3\cdot 2^{5n-2}$$.

**Solution:**
First note that

$$5^{2n}=25(25)^{n-1} \equiv 4\cdot 4^{n-1}\mod 5$$

and also

$$3\cdot 2^{5n-2} = 24\cdot 32^{n-1}\equiv 3\cdot 4^{n-1}\mod 7$$.

Therefore 

$$5^{2n} + 3\cdot 2^{5n-2}\equiv 4\cdot 4^{n-1} + 3\cdot 4^{n-1}\mod 7 \equiv 0\mod 7.$$

:black_square_button:


:warning: **Take care with division**:  If $$a=b\mod n$$, then $$ac=bc\mod n$$.  However, the converse isn't necessarily true!

For example $$12=6\mod 6$$ but $$4\neq 2\mod 6$$.  In other words, we are not always able to *divide* and preserve modular equivalence, even if we have a common factor to divide by!

However, in some cases it is allowed, as we can see from the following theorem.

**Theorem:** Suppose $$ac\equiv bc\mod n$$ and let $$d=\gcd(c,n)$$.  Then $$a \equiv bc\mod n/d$$.

**Proof:**  Suppose that $$ac\equiv bc\mod n$$.  Then there exists $$k$$ with

$$ac-bc = nk.$$

Furthermore, we can choose $$x,y\in\mathbb{Z}$$ satisfying $$cx+ny=d$$.
Then

$$(a-b)(c/d) = (n/d)k$$

In particular $$(c/d)$$ divides $$(n/d)k$$.  Since $$\gcd(c/d,n/d) = 1$$, it follows that $$(c/d)$$ divides $$k$$, ie. $$k=m(c/d)$$.  It follows that $$(a-b)=(n/d)m$$ and therefore $$a\equiv b\mod m$$.

**Corollary:** If $$ac\equiv bc\mod n$$ with $$c$$ and $$n$$ relatively prime, then $$a\equiv b\mod n$$.

## Remainders

The Division Algorithm tells us that every integer must be equivalent to one of the values $$0,1,2,\dots,n-1$$ modulo $$n$$.
In fact, the Division Algorithm provides a nice characterization of modular equivalence.

**Theorem:** Two integers $$a$$ and $$b$$ are equivalent modulo $$n$$ if and only if they have the same nonnegative remainder when divided by $$n$$.

**Example Problem:**  Find the remainder after dividing $$1! + 2! + 3! + 4! + 5! + 2023!$$ by $$12$$.

**Solution:** Most of the terms in the sum are equivalent to $$0\mod 12$$, so the full sum is equivalent to $$1!+2!+3!=9$$.  Therefore the remainder is $$9$$.
:black_square_button:




