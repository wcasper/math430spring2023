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
* (f) if $$a\mid b$$ and $$b\neq 0$$ then $$|a|\leq |b|$$
* (g) if $$a\mid b$$ and $$a\mid c$$ then $$a\mid (bx + cy)$$ for all integers $$x$$ and $$y$$


## Greatest common divisor

Given a collection of integers $$a_1, a_2,\dots, a_n$$, the **greatest common divisor** of the collection is the largest integer $$d$$ with the property that $$d \mid a_k$$ for all $$k$$.


**Theorem:** Let $$d$$ be the greatest common divisor of $$a_1,\dots, a_n$$.  Then there exist integers $$x_1,\dots, x_n$$ satisfying

$$d = a_1x_1 + a_2x_2 + \dots + a_nx_n.$$

**Corollary:**  Let $$d$$ be the greatest common divisor of $$a_1,\dots, a_n$$.  The set of all integers of the form

$$a_1x_1 + a_2x_2 + \dots + a_nx_n$$

is precisely the set of all integer multiples of $$d$$.


