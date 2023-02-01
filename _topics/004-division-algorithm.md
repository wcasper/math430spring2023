---
layout: page
title: Division algorithm
---

The **Division Algorithm** is one of the most basic tools in number theory, and plays a fundamental role in the divisibility theory of integers.

**Theorem (Division Algorithm):**
Let $$a$$ and $$b$$ be integers with $$b>0$$.  Then there exist unique integers $$q$$ and $$r$$ satisfying

$$a = qb + r,\quad\text{with},\ 0\leq r < b.$$

The integers $$q$$ and $$r$$ are called the **quotient** and the **remainder** respectively.
Put another way, this theorem says that we are always able to *simplify* a fraction $$a/b$$ as

$$\frac{a}{b} = q + \frac{r}{b}$$

for unique choices of integrs $$q$$ and $$r$$ if we enforce $$0\leq r < b$$.

Note the Division Algorithm is often extended to the case $$b < 0$$ by using the absolute value.

**Corollary:** 
Let $$a$$ and $$b$$ be integers with $$b\neq 0$$.  Then there exist unique integers $$q$$ and $$r$$ satisfying

$$a = qb + r,\quad\text{with},\ 0\leq r < |b|.$$

## Proof of the Division Algorithm:

In order to prove the Division algorithm, we will need to apply the **Well-Ordering Principle**, one of the fundamental properties of the natural numbers.

**Well-ordering Principle:** Every nonempty set $$S$$ of non-negative integers has a **least element**, an element $$a\in S$$ such that $$a\leq b$$ for all $$b\in S$$.

The Well-ordering Principle is not a Theorem.
It's actually an **axiom**, forming one of the five **Peano Axioms**.
As such, we don't prove it.  We just take it to be true, based on our intuition about how integers should work.
Using the Well-ordering Principle, one can prove that mathematical induction is true.
Alternatively, one can take as an axiom that induction is true (the so-called **Axiom of Induction**), and use it to prove the Well-ordering Principle.
In other words, the Axiom of induction and the Well-ordering Principle are **equivalent**.

With this in mind, we can prove the division algorithm.

**Proof of the Division Algorithm:**

Consider the set

$$S = \{a-xb: x\in \mathbb{Z},\quad a-xb\geq 0\}.$$

Obviously, any element of this set will be non-negative.
Furthrmore, if we were to let $$x=-|a|$$ then

$$a-xb = a+|a|b \geq -|a| + |a|b = |a|(b-1)\geq 0.$$

Therefore for this value of $$x$$, the element $$a-xb$$ belongs to $$S$$.  In particular, $$S$$ is nonempty.

Thus $$S$$ is a non-empty set of non-negative integers.  By the Well-ordering Principle, $$S$$ has a smallest element $$q$$.
By definition

$$r = x-qb\quad\text{satisfies}\ r\geq 0.$$

We claim that $$r < b$$.
To see this, assume otherwise.
Then this would mean

$$x-(q+1)b = x-qb-q = r-q\geq 0.$$

In particular, $$r-q$$ is an element of $$S$$ less than $$r$$, contradicting the defintion of $$r$$.
Hence $$r < b$$.

To complete the proof, we need to show that the values of $$q$$ and $$r$$ that we found above are unique.
To see this, suppose that $$q'$$ and $$r'$$ are also integers satisfying

$$a = q'b + r',\quad\text{with},\ 0\leq r' < b.$$

Then we see that

$$0 = a-a = (qb+r)-(q'b+r') = (q-q')b + r-r'.$$

In particular $$(q-q')b = -(r-r')$$.  Since both $$r$$ and $$r'$$ are nonnegative and strictly less than $$b$$, 

$$|q-q'|b = |r-r'| < b.$$

Therefore $$\lvert q-q'\rvert < 1$$, forcing $$q=q'$$.  Inserting this in the previous equation, we get $$r=r'$$ also.


**Problem:** Show that $$n(n+1)/2$$ is an integer for all integers $$n$$.

**Problem:** Show that $$n(n^2+1)/3$$ is an integer for all integers $$n$$.



