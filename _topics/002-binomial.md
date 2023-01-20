---
layout: page
title: Binomial theorem
---

Binomial coefficients are positive numbers associated with the expansion of expressions of the form $$(x+y)^n$$.
Moreover, they have interesting interpretations in terms of other mathematical topics, such as combinatorics.


## Basic definition and facts

The binomial coefficient $$\binom{n}{k}$$ is defined by

$$\binom{n}{k} = \frac{n!}{k!(n-k)!},\quad 0\leq k\leq n.$$

Here $$n$$ and $$k$$ are integers and $$n! = n(n-1)(n-2)\dots 1$$ is $$n$$ **factorial**.
Note that by convention $$0!=1$$.
Interestingly, binomial coefficients are also integers, though that is not at all obvious from the expression above.

To see this, we first establish **Pascal's identity**.

**Theorem (Pascal's Identity):**

Let $$n\leq k\leq 1$$ be integers.  Then

$$\binom{n}{k} + \binom{n}{k-1} = \binom{n+1}{k}.$$

**Proof:**

The proof of this fact amounts to just performing a bit of algbraic simplification.
In fact

$$\begin{align*}
\binom{n}{k}+\binom{n}{k-1}
  &= \frac{n!}{k!(n-k)!}+\frac{n!}{(k-1)!(n-k+1)!}\\
  &= \frac{n!}{(k-1)!k(n-k)!}+\frac{n!}{(k-1)!(n-k)!(n-k+1)}\\
  &= \frac{n!}{(k-1)!(n-k)!}\left(\frac{1}{k}+\frac{1}{n-k+1}\right)\\
  &= \frac{n!}{(k-1)!(n-k)!}\left(\frac{n+1}{k(n-k+1)}\right)\\
  &= \frac{(n+1)!}{k!(n-k+1)!} = \binom{n+1}{k}.
\end{align*}$$

:black_square_button:

This immediately gives us a way of calculating binomial coefficients, called **Pascal's Triangle**

$$
\begin{tabular}{rccccccccc}
$n=0$:&    &    &    &    &  1\\\noalign{\smallskip\smallskip}
$n=1$:&    &    &    &  1 &    &  1\\\noalign{\smallskip\smallskip}
$n=2$:&    &    &  1 &    &  2 &    &  1\\\noalign{\smallskip\smallskip}
$n=3$:&    &  1 &    &  3 &    &  3 &    &  1\\\noalign{\smallskip\smallskip}
$n=4$:&  1 &    &  4 &    &  6 &    &  4 &    &  1\\\noalign{\smallskip\smallskip}
\end{tabular}
$$

Here the $$n$$'th row has entries $$\binom{n}{0},\binom{n}{1},\dots,\binom{n}{k}$$.
Pascal's triangle can be easily constructed from Pascal's identity, using the
fact that the left and right sides of the triangle are all one's and that each
inner entry of the triangle must be the sum of the two numbers to the left and
right in the preceeding row.

Note in particular that Pascal's Triangle shows us that all the binomial coefficients will be integers!
To prove this formally, you can proceed by induction on the row $$n$$.
This is a great exercise if you are looking for more practice with inductive arguments.

## Binomial theorem

One of the most useful properties of binomial coefficients is their appearance in as coefficients in the expansion of an expression of the form $$(x+y)^n$$.

For example, we can calculate

$$(x+y)^0 = 1$$

$$(x+y)^1 = x + y$$

$$(x+y)^2 = x^2 + 2xy + y^2$$

$$(x+y)^3 = x^3 + 3x^2y + 3xy^2 + y^3$$

from which we see the same coefficients as in Pascal's Triangle showing up.
This motivates the following theorem.

**Binomial Theorem:** 

The expansion of the $$(x+y)^n$$ is given by

$$(x+y)^n = \sum_{k=0}^n\binom{n}{k}x^ky^{n-k}.$$

In particular, the coefficient of $$x^ky^{n-k}$$ in the expansion of $$(x+y)^n$$ is $$\binom{n}{k}$$.

**Proof:**

To prove this, we will use induction on $$n$$.

As we already saw above, the statement holds for $$n=0$$ and $$n=1$$.

Let $$m\geq 1$$ be an integer.
As an inductive assumption, suppose that the statement of our theorem holds for $$n=m$$.
In other words, assume

$$(x+y)^m = \sum_{k=0}^m\binom{m}{k}x^ky^{m-k}.$$

Then we calculate

$$\begin{align*}
(x+y)^{m+1}
  &= (x+y)(x+y)^m\\
  &= (x+y)\sum_{k=0}^m\binom{m}{k}x^ky^{m-k}\\
  &= x\sum_{k=0}^m\binom{m}{k}x^ky^{m-k} + y\sum_{k=0}^mx^ky^{m-k}\\
  &= \sum_{k=0}^m\binom{m}{k}x^{k+1}y^{m-k} + \sum_{k=0}^m\binom{m}{k}x^ky^{m-k+1}\\
  &= x^{m+1} + \sum_{k=0}^{m-1}\binom{m}{k}x^{k+1}y^{m-k} + \sum_{k=1}^m\binom{m}{k}x^ky^{m-k+1} + y^{m+1}.
\end{align*}$$

Now by reindexing the first sum, we get

$$\begin{align*}
(x+y)^{m+1}
  &= x^{m+1} + \sum_{k=1}^{m}\binom{m}{k-1}x^{k}y^{m-k+1} + \sum_{k=1}^m\binom{m}{k}x^ky^{m-k+1} + y^{m+1}\\
  &= x^{m+1} + \sum_{k=1}^{m}\left(\binom{m}{k-1}+\binom{m}{k}\right)x^{k}y^{m-k+1} + y^{m+1}.
\end{align*}$$

Finally, by using Pascal's identity we find

$$\begin{align*}
(x+y)^{m+1}
  &= x^{m+1} + \sum_{k=1}^{m}\binom{m+1}{k}x^{k}y^{m-k+1} + y^{m+1}\\
  &= sum_{k=0}^{m+1}\binom{m+1}{k}x^{k}y^{m+1-k}.
\end{align*}$$

Thus the statement of our theorem is true for $$n=m+1$$.
By the principle of mathematical induction, it therefore holds for all $n\geq 0$$.
:black_square_button:

## Combinatorial interpretation

Interestingly, binomial coefficients have very important applications in other fields such as combinatorics and statistics.
This comes from the following combinatorial interpretation of $$\binom{n}{k}$$.

**Theorem:**  Let $$S$$ be a set with $$n$$ elements.  The number subsets of $$S$$ with $$k$$ elements is $$\binom{n}{k}.$$

In other words, the number of ways of choosing $$k$$ elements out of a collection of $$n$$ elements without paying attention to order or being allowed to repeat choices is $$\binom{n}{k}$$.
For this reason, $$\binom{n}{k}$$ is sometimes referred to as **$$n$$ choose $$k$$**.


