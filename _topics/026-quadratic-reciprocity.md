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

We will provide one of the most accessible proofs of quadratic reciprocity, but as a starting point we require a Lemma which provides yet another expression for quadratic residues.

**Theorem:**  Let $$p$$ be an odd prime and $$a$$ an odd integer with $$\gcd(a,p) = 1$$.  Then

$$(a/p) = (-1)^{\sum_{k=1}^{(p-1)/2} \lfloor ak/p\rfloor}.$$

**Proof:**

For each $$k$$, let $$t_k$$ be the remainder of $$ak$$ divided by $$p$$.

Then

$$\begin{align}
\sum_{k=1}^{(p-1)/2} ak
  & = \sum_{k=1}^{(p-1)/2} \left(\lfloor \frac{ak}{p}\rfloor p  + r_k\right).
\end{align}$$

Moreover, from the proof of Gauss's Lemma we know that

$$\lvert r_1 \rvert_p, \lvert r_2 \rvert_p,\dots \lvert r_{(p-1)/2}\rvert$$ 

are just the numbers $$1,2,\dots, (p-1)/2$$ in some order.  Therefore

$$\begin{align}
\sum_{k=1}^{(p-1)/2} k
  & = \sum_{k=1}^{(p-1)/2} \lvert r_k\rvert_p.
\end{align}$$

Let $$n$$ be as in th statement of Gauss's Lemma and let $$E\subseteq \{1,2,\dots, (p-1)/2\}$$ consist of all integers $$k$$ with $$r_k\neq \lvert r_k\rvert_p.$$
Putting these together, we find for $$n$$ defined as in the statement of Gauss's Lemma

$$\begin{align}
\sum_{k=1}^{(p-1)/2} (a-1)k
  & = \sum_{k=1}^{(p-1)/2} \left(\lfloor \frac{ak}{p}\rfloor p  + r_k\right) - \sum_{k=1}^n \lvert r_k\rvert_p\\
  & = \sum_{k=1}^{(p-1)/2} \left(\lfloor \frac{ak}{p}\rfloor p  + r_k-\lvert r_k\rvert_p\right)\\
  & = \sum_{k=1}^{(p-1)/2} \left(\lfloor \frac{ak}{p}\rfloor p\right) + np + 2\sum_{k\in E} r_k.
\end{align}
$$

Reducing this expressiion modulo $$2$$, using the fact that both $$a$$ and $$p$$ are odd, we find

$$0 \equiv n + \sum_{k=1}^{(p-1)/2} \lfloor \frac{ak}{p}\rfloor\mod 2.$$

Thus by Gauss's Lemma

$$(a/p) = (-1)^n = (-1)^{\sum_{k=1}^{(p-1)/2} \lfloor ak/p\rfloor}.$$

:black_square_button:


Using this, we are now equipped to prove quadratic reciprocity.

**Proof of quadratic reciprocity:**

Consider the positive integer-valued points $$(j,k)$$ inside the rectangle $$R$$ $$[0,p/2]\times [0,q/2]$$ in the $$(x,y)$$ plane.
Split the rectangle $$R$$ into two triangles, using the line $$y=(q/p)x$$ which passes through the points $$(0,0)$$ and $$(q/2,p/2).$$
Since $$p$$ and $$q$$ are relatively prime, no positive integer pairs $$(j,k)$$ lie directly on this line.

The total points in the rectangle are $$\frac{p-1}{2}\cdot\frac{q-1}{2}.$$
The number of points in the lower triangle is

$$\sum_{j=1}^{(p-1)/2} \lfloor qj/p\rfloor,$$

while the number of points in the upper triangle is

$$\sum_{j=1}^{(q-1)/2} \lfloor pj/q\rfloor.$$

Hence we obtain

$$\sum_{j=1}^{(p-1)/2} \lfloor qj/p\rfloor + \sum_{j=1}^{(q-1)/2} \lfloor pj/q\rfloor = \frac{p-1}{2}\frac{q-1}{2}.$$

It follows that

$$(-1)^{\frac{p-1}{2}\frac{q-1}{2}} = (-1)^{\sum_{j=1}^{(p-1)/2} \lfloor qj/p\rfloor}(-1)^{\sum_{j=1}^{(q-1)/2} \lfloor pj/q\rfloor} = (q/p)(p/q).$$

:black_square_button:


Sometimes quadratic reciprocity takes on the following, somewhat computationally friendlier statement.

$$(p/q) = \left\lbrace\begin{array}{cc}
 (q/p) & p\equiv 1\ \text{or}  q\equiv 1\mod 4\\
-(q/p) & p\equiv 3\ \text{and} q\equiv 3\mod 4\\
\end{array}\right.$$



