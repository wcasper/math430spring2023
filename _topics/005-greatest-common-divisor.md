---
layout: page
title: Greatest common divisor
---

## Divisors

An integer $$b$$ is said to **divide** $$a$$ if there exists an integer $$c$$ with $$a = bc$$.  In this case, we write $$b\mid a$$ and call $$b$$ a **divisor** or **factor** of $$a$$, and we call $$a$$ a multiple of $$b$$.

If $$b$$ does not divide $$a$$, we may write $$b\nmid a$$.

The following theorem captures some basic properties of divisors.

**Theorem:** For any integers $$a,b,c$$ the following hold.

* (a) $$a\mid 0$$, $$1\mid a$$, $$a\mid a$$
* (b) $$a\mid 1$$ if and only if $$a = \pm 1$$
* (c) if $$a\mid b$$ and $$c\mid d$$, then $$ac\mid bd$$
* (d) if $$a\mid b$$ and $$b\mid c$$ then $$a\mid c$$
* (e) $$a\mid b$$ and $$b\mid a$$ if and only if $$a = \pm b$$
* (f) if $$a\mid b$$ and $$b\neq 0$$ then $$\lvert a\rvert \leq \lvert b\rvert$$
* (g) if $$a\mid b$$ and $$a\mid c$$ then $$a\mid (bx + cy)$$ for all integers $$x$$ and $$y$$

As a more general version of (g), we have the following.

**Corollary:**

Suppose that $$d$$ is an integer which divides every integer in the collection $$a_1, a_2,\dots, a_n$$.
Then for any integers $$x_1,\dots, x_n$$ we have

$$a\mid (a_1x_1 + a_2x_2 + \dots + a_nx_n).$$

## Greatest common divisor

Given a collection of integers $$a_1, a_2,\dots, a_n$$, the **greatest common divisor** of the collection is the largest integer $$d$$ with the property that $$d \mid a_k$$ for all $$k$$.
In terms of notation, we denote the greatest common divisor as $$\gcd(a_1,a_2,\dots, a_n).$$

One fundamentally important property of greatest common divisors is that they can be expressed as *integer* combinations of the elements that they divide.

**Theorem:** Let $$d$$ be the greatest common divisor of $$a_1,\dots, a_n$$.  Then there exist integers $$x_1,\dots, x_n$$ satisfying

$$d = a_1x_1 + a_2x_2 + \dots + a_nx_n.$$

As a consequence, we have a very simple description of the set of all integer combinations of a finite collection of integers.

**Corollary:**  Let $$d$$ be the greatest common divisor of $$a_1,\dots, a_n$$.  The set of all integers of the form

$$a_1x_1 + a_2x_2 + \dots + a_nx_n$$

is precisely the set of all integer multiples of $$d$$.
In other words,

$$\{a_1x_1 + a_2x_2 + \dots + a_nx_n: x_1,\dots, x_n\in\mathbb{Z}\} = \{qd: q\in\mathbb{Z}\}.$$

This fact results in the following theorem, which is sometimes used as an alternative definition of the greatest common divisor of a collection of integers.

**Theorem:** Let $$d$$ be a positive integer.  Then $$d$$ is the greatest common divisor of $$x_1,\dots,x_n$$ if and only if it satisfies the following two properties.
* $$d\mid x_k$$ for all $$k=1,\dots, n$$
* if $$c\mid x_k$$ for all $$k=1,\dots, n$$, then $$c\mid d$$.

Next, we focus on the special case when the greatest common divisor is $$1$$.

**Definition:** A pair of integers are called **relatively prime** if their greatest common divisor is $$1$$.

**Theorem:** A pair of integers $$a$$ and $$b$$ are relatively prime if and only if there exist integers $$x$$ and $$y$$ satisfying

$$ax + by = 1.$$

We can relate the relatively prime situation to more general greatest common divisors.

**Corollary:** If $$\gcd(a,b) = d$$ then $$\gcd(a/d,b/d) = 1$$.

In particular, this provides us with a nice condition for when the product of a pair of integers will be a divisor.

**Corollary:** If $$a\mid c$$ and $$b\mid c$$ with $$\gcd(a,b) = 1$$ then $$ab \mid c$$.

Likewise, we can get a characterization of what part of the product of a pair of integers something divides.

**Euclid's Lemma:** If $$a \mid bc$$ with $$\gcd(a,b) = 1$$ then $$a\mid c$$.

## Least common multiple

When comparing pairs of numbers $$a,b$$ we often consider a quantity related to their greatest common divisor, called their least common multiple.

**Definition:** The **least common multiple** of a collection of integers $$a_1,\dots, a_n$$ is an integer $$m > 0$$ satisfying the following two properties:
* $$a_k \mid m$$ for all $$1\leq k \leq n$$ 
* if $$c > 0$$ satisfies $$a_k \mid c$$ for all $$1\leq k\leq n$$ then $$m\geq c$$

Notationally, we denote the least common multiple as $$\lcm(a_1,a_2,\dots, a_n).$$

The greatest common divisor and least common multiple of a pair of integers are related by the following result.

**Theorem:** Let $$a$$ and $$b$$ be positive integers.  Then

$$\gcd(a,b)\lcm(a,b) = ab.$$

**Proof:**

Let $$d = \gcd(a,b)$$ and consider $$m = ab/d$$.  We must show that $$m = \lcm(a,b)$.

Since $$d$$ divides both $$a$$ and $$b$$, there exist integers $$p$$ and $$q$$ with $$a = pd$$ and $$b = qd$$.  It follows that $$m = pb = aq$$, so $$m$$ divisible by both $$a$$ and $$b$$.

Now suppose $$c>0$$ is divisible by both $$a$$ and $$b$$.
We know that there exist integers $$x,y$$ with $$d = ax + by$$.  Therefore

$$\frac{c}{m} = \frac{cd}{ab} = \frac{c(ax + by)}{ab} = \frac{c}{b}x + \frac{c}{a}y.$$

Since the right hand side is an integer, this proves $$m$$ must divide $$c$$ and therefore $$m\leq c$$.
Thus $$m = lcm(a,b)$$.
:black_square_button:

Note that in the proof, we actually showed the following fact:

* if $$c > 0$$ is divisible by both $$a$$ and $$b$$, then $$\gcd(a,b)\mid c$$

This is sometimes used as the *definition* of the least common multiple.


