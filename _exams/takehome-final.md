---
layout: page
title: Final Takehome Portion
permalink: /exams/takehome-final
---

Solve each of the following problems.
If the problem asks for a proof, be sure to carefully justify your work, including any theorems from class.

Note: you may NOT use a theorem or result from class to prove something when it makes the problem entirely trivial.  If you are unsure whether a particular theorem or result is allowed, just ask!


## Problem 1

Suppose that $$f$$ and $$g$$ are arithmetic functions.

* (a)  Prove that Dirichlet convolution satisfies $$f* g = g * f$$

* (b)  Suppose that $$f(ab) = f(a)f(b)$$ for all integers $$a,b$$ (not nec. coprime).  Prove that for all $$n\geq 1$$

$$(f * f)(n) = f(n)\tau(n).$$

## Problem 2

Consider the circle of radius $$8$$.

$$x^2 + y^2 = 64.$$

Show that if $$(a,b)$$ is an integer point on the circle, then $$a$$ and $$b$$ are not both perfect squares.

[Hint: try reducing modulo $$5$$]


## Problem 3

Suppose that $$p$$ and $$q$$ are odd primes with $$\gcd(p,a)=1$$ and $$p=\pm q\mod 4a$$.  Then

$$(a/p) = (a/q).$$

Hints/roadmap:
1. Since Legendre symbols are multiplicative, it suffices to consider the case when $$a$$ is prime.
2. If $$a=2$$, use our special formula for $$(2/p)$$ and $$(2/q)$$
3. If $$a$$ is an odd prime, use reciprocity to write

$$(a/p) = (-1)^{\frac{a-1}{2}\frac{p-1}{2}} (p/a) = (-1)^{\frac{a-1}{2}\frac{p-1}{2}} (\pm q/a).$$

(where here we've used that $$p$$ is equivalent to $$\pm q$$ modulo $$a$$.)

4.  Now use $$(\pm 1/ a) = (\pm 1)^{(a-1)/2}$$ and quadratic reciprocity again on $$(q/a)$$.


