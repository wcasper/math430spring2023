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


Ultimately, our goal is to find a way to rapidly evaluate legendre symbols, since they in turn allow us to decide whether a particular quadratic congruence equation is solvable.
Thus we are motivated to investigate more detailed properties of Legendre symbols.
Take for example the following theorem, which says that there are exactly the same number of quadratic residues mod $$p$$ as there are quadratic nonresidues.

**Theorem:**  If $$p$$ is an odd prime then

$$\sum_{a=1}^{p-1} (a/p) = 0.$$

**Proof:**

Choose a primitive root $$b$$ modulo $$p$$.  Then for each $$1\leq a\leq p-1$$ there exists a unique $$1\leq k \leq p-1$$ with $$a = b^k$$.
Therefore geometric sums tell us

$$\sum_{a=1}^{p-1} (a/p) \equiv \sum_{k=1}^{p-1}(b^k/p) \equiv \sum_{a=1}^{p-1} b^{(p-1)k/2} = 0.$$

Since the summands of $$\sum_{a=1}^{p-1} (a/p)$$ are all either $$1$$ or $$-1$$, we know that 

$$\left\lvert \sum_{a=1}^{p-1} (a/p)\right\rvert \leq \sum_{a=1}^{p-1} |(a/p)| = p-1.$$

Therefore $$\sum_{a=1}^{p-1} (a/p)$$ is an integer between $$-(p-1)$$ and $$(p-1)$$, which is equivalent to $$0$$ mod $$p$$.
Thus the only thing it could be is identically zero.
:black_square_button:

Our proof actually shows much more, which we summarize in the following corollary.

**Corollary:** The quadratic residues mod $$p$$ are precisely the even powers of a primitive element modulo $$p$$.


### Gauss's Lemma

As we have seen previously, Gauss has a habit of refining and expanding on the work of Euler.  The exploration of the Legendre symbol is no different in this respect.
We are moving toward a very powerful result about Legendre symbols called quadratic reciprocity, which allows us to relate symbols with different prime moduli.
The following lemma, called Gauss's Lemma is a key result along the way.

**Theorem (Gauss's Lemma):**  Let $$p$$ be an odd prime and suppose that $$\gcd(a,p) = 1$$.  If $$n$$ denotes the number of integers in the set

$$\left\lbrace a,2a,3a,\dots, \frac{p-1}{2}a\right\rbrace$$

whose remainders when divided by $$p$$ exceed $$p/2$$, then

$$(a/p) = (-1)^n.$$

**Proof:**

For any integer $$b$$, let $$0\leq r_b < p$$ be the remainder of $$b$$ divided by $$p$$.

To prove our statement, we introduce the absolute value modulo $$p$$.

$$\lvert k\rvert_p = \left\lbrace\begin{array}{cc} k & 0\leq k < p/2\\ p-k & p/2 < k < p\end{array}\right.$$

Notice that if $$\lvert r_c\rvert_p = \lvert r_b\rvert_p$$, then either $$r_c=r_b$$ or $$r_c+r_b=p$$.  Hence either $$c\equiv b$$ modulo $$p$$ or $$c\equiv -b$$ modulo $$p$$.

Thus if both $$1\leq b,c\leq (p-1)/2$$ then $$\lvert r_{ab}\rvert_p =\lvert r_{ac}\rvert_p$$ implies $$ab\equiv ac$$ or $$ab\equiv -ac$$.  Since $$a$$ is invertible, this means that $$b\equiv c$$ or $$b\equiv -c$$, but from the relative proximity of $$b$$ and $$c$$, we see that $$b=c$$.  Hence the sequence

$$\lvert r_a\rvert_p,\ \lvert r_{2a}\rvert_p,\ \lvert r_{3a}\rvert_p\ \dots \lvert r_{(p-1)a/2)}\rvert_p$$

is a permutation of

$$1,2,\dots, (p-1)/2$$.

It follows that

$$\left(\frac{p-1}{2}\right)! = \lvert r_a\rvert_p\cdot \lvert r_{2a}\rvert_p\dots \lvert r_{(p-1)a/2}\rvert_p \equiv \left(\frac{p-1}{2}\right!a^{(p-1)/2}(-1)^n.$$

Hence $$(-1)^n\equiv a^{(p-1)/2}$$ and the statement of the theorem follows from Euler's Theorem.
:black_square_button:


This lemma facilitates many interesting calculations, such as the value of $$(2/p)$$.

**Theorem:**  Let $$p$$ be an odd prime.  Then 

$$(2/p) = (-1)^{\frac{p-1}{2}-\lfloor \frac{p}{4}\rfloor}.$$

**Proof:**

We are considering the number $$n$$ of elements in the set 

$$\left\lbrace 2,4,6,\dots, p-1\right\rbrace$$

whose remainders modulo $$p$$ are greater than $$p/2$$.  Each value in the set is between $$1$$ and $$p-1$$, so they are their own remainders modulo $$p$$.
The subset

$$\left\lbrace 2,4,6,\dots, 2\lfloor p/4\rfloor \right\rbrace$$

is the subset of the values less than $$p/2$$, so 

$$n = \left\lvert\left\lbrace 2,4,6,\dots, p-1\right\rbrace\right\rvert - \left\lvert\left\lbrace 2,4,6,\dots, 2\lfloor p/4\rfloor \right\rbrace\right\rvert = \frac{p-1}{2}-\lfloor p/4\rfloor.$$

The statement of our theorem follows immediately from Gauss's Lemma.
:black_square_button:

There's a nice, compact way of rephrasing this.

**Corollary:**  Let $$p$$ be an odd prime.  Then

$$(2/p) = (-1)^{(p^2-1)/8}.$$


