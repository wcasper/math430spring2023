---
layout: page
title: Diophantine equations
---

Many kinds of equations which arise naturally imply or require the existence of *integer*-valued solutions.
For example, suppose I buy a sandwich for $$7$$ dollars and $$50$$ cents, using a collection of quarters, dimes and nickels.
The number of quarters I use is half the number of dimes and nickels put together.
So how many coins did I use, and what were they?

We can represent the quarters, nickels and dimes in terms of some variables $$q,n,d$$.  Then mathematically, we know

$$\frac{1}{4}q + \frac{1}{10}d + \frac{1}{20}n = \frac{15}{2},$$

and 

$$q  = \frac{1}{2}(d+n).$$

Substituting in for $$q$$, we get the single equation

$$\frac{9}{40}d + \frac{7}{40}n = \frac{15}{2}.$$

Mathematically, this has infinitely many solutions.  However, realistically our solution only makes sense if $$d$$ and $$n$$ are *positive* and *whole numbers*.
This actually means that there are only a finite number of solutions, specifically the five solutions

| q  | d  | n  |
| -- | -- | -- |
| 42 |  3 | 39 |
| 40 | 10 | 30 |
| 38 | 17 | 21 |
| 36 | 24 | 12 |
| 34 | 31 |  3 |

As another example, we could consider a Platonic solid (ie. regular polyhedron).  If each face of the polyhedron has $$p$$ sides and each vertex touches $$q$$ faces, one can use basic geometry to prove

$$\frac{1}{p} + \frac{1}{q} > \frac{1}{2},$$

or equivalently

$$(p-2)(q-2) < 4.$$

The positive integer values satisfying this condition are precisely 

| p | q | polyhedron |
| - | - | ---------- |
| 3 | 3 | tetrahedron |
| 3 | 4 | octahedron |
| 4 | 3 | cube |
| 3 | 5 | icosahedron | 
| 5 | 3 | dodecahedron |

What these solutions are and how to find them is part of the study of *Diophantine equations*.

**Definition:** A **Diophantine equation** is a polynomial equation in one or more variables with rational coefficients.

Thus

* $$1 - x + x^2 - x^3 + x^4 = 7$$
* $$3x + 2y = 4$$
* $$x^3 + y^3 = z^3$$
* $$y^2 = x^3 + 3x - 2$$

are all examples of Diophantine equations.

## Linear Diophantine equations

As a special case of Diophantine equations, we can consider ones where our variables are not being multiplied by one another.

**Definition:** A linear Diophantine equation is an equation of the form

$$a_1x_1 + a_2x_2 + \dots + a_nx_n = c.$$

We will mostly consider the special case of the two-variable version, which looks like

$$ax + by = c.$$

Of course, equations like this don't need to have solutions at all.

**Example:**  $$2x + 4y = 7$$ has no solution because the left hand side will always be even.

**Theorem:**  The Diophantine equation $$ax+by = c$$ has a solution if and only if the greatest common divisor of the coefficients $$d = \gcd(a,b)$$ divides $$c$$.

**Theorem:**  Let $d = \gcd(a,b)$ and suppose that the Diophantine equation $$ax+by = c$$ has a solution $$x=x_0$$ and $$y=y_0$$.  Then

$$x = \left(x_0 + \frac{b}{d}t\right), & y = \left(y_0 - \frac{a}{d}t\right)$$

is a solution for all $$t\in\mathbb{Z}$$ and moreover every solution of the Diophantine equation is of this form.


