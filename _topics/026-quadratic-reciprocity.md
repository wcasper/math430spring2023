---
layout: page
title: Quadratic reciprocity
---


As maybe the most beautiful result of the course, we have the Quadratic Reciprocity Law, which relates Legendre symbols of *different* primes.
The statement itself is deceptively simple and incredibly useful.

**Theorem (Quadratic Reciprocity):**

Let $$p$$ and $$q$$ be two distinct odd primes.  Then

$$(p/q)(q/p) = (-1)^{\frac{p-1}{2}\frac{q-1}{2}}.$$


Alternatively, we can say

$$(p/q) = \left\lbrace\begin{array}{cc}
 (q/p) & p\equiv 1\mod 4\ \text{or}\ q\equiv 1\mod 4\\
-(q/p) & p\equiv 3\mod 4\ \text{and}\ q\equiv 3\mod 4\\
\end{array}\right.

This is incredibly useful in calculating Legendre symbols, when combined with the properties of Legendre symbols and the three special cases:

$$(1/p) = 1,\ \ \ (-1/p) = (-1)^{(p-1)/2},\ \ \ (2/p) = (-1)^{(p^2-1)/8}.$$

**Example:**

Let's calculate $$(71/73).$$

By quadratic reciprocity

$$(71/73) = (73/71) = (2/71) = (-1)^{(71^2-1)/8} = 1.$$


**Example:**

Let's calculate $$(1234/4567).$$

We have

$$(1234/4567) = (2/4567)(617/4567).$$

Now by quadratic reciprocity

$$(617/4567) = (4567/617) = (248/617) = (2/617)(31/617).$$

Again

$$(31/617) = (617/31) = (28/31) = (4/31)(7/31) = (7/31).$$

and

$$(7/31) = -(31/7) = -(3/7) = (7/3) = (1/3).$$

Putting it all together, we get

$$(1234/4567) = (2/4567)(2/617)(1/3) = 1.$$


## Proving quadratic reciprocity

Proving quadratic reciprocity is actually pretty challenging.
The first proof was found by Gauss, after working on the problem for more than a year.
Gauss himself actually found several very different proof of quadratic reciprocity, as have many other mathematicians later on, including proofs involving high powered tools like Dirichlet L-functions.

We will provide one of the most accessible proofs of quadratic reciprocity, 








