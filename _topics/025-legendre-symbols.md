---
layout: page
title: Legendre symbols
---

**Definition:** Let $$p$$ be an odd prime.  The **Legendre symbol**  $$(a/p)$$ is given by

$$(a/p) = \left\lbrace\begin{array}{cc}1&a\ \text{is a quadratic residue}\\0&a\ \text{is not a quadratic residue}\end{array}\right.$$

As we learned from Euler's criterion, $$(a/p)$$ and $$a^{(p-1)/2}$$ will have the same value modulo $$p$$.
This leads to several basic properties of Legendre symbols, whose proofs are fairly obvious.

**Theorem:**
Let $$p$$ be an odd prime, and let $$a,b$$ be integers both not divisible by $$p$$.
Then the following hold.
* Modularity: if $$a\equiv b\mod p$$ then $$(a/p)\equiv (b/p)$$
* Multiplicativity: $$(ab/p) = (a/p)(b/p)$$

Note as a special cases of multiplicativity, we know

$$(a^2/p) = (a/p)^2 = (\pm 1)^2 = 1$$

With $$a=1$$, this gives $$(1/p)\equiv 1$$.

Furthermore, $$(-1/p) \equiv (-1)^{p-1}$$ and both are either $$1$$ or $$-1$$ so we actually have equality $$(-1/p) = (-1)^{p-1}$$.

To summarize, we have the following special values for Legendre symbols.

**Theorem:**
* $$(a^2/p) = 1$$
* $$(1/p) = 1$$
* $$(-1/p) = (-1)^{(p-1)/2}$$

