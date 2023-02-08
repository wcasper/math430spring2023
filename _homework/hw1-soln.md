---
layout: page
title: Homework 1 Solution
permalink: /homework/hw1-soln
---

### Directions
Solve the following problems and type up your solutions.  Your solutions should be provided in one of the following formats (in order of preference)
* typed up in $$\LaTeX$$ and submitted as a PDF on Canvas
* written legibly on blank paper, scanned into a PDF and then uploaded on Canvas
* written on ancient parchement with a quill and then flown to the instructor via owl post like in Harry Potter

If you go with the first strategy, you may wish to check out Overleaf which is a free and intuitive website for generating $$\LaTeX$$ documents online.
If you wish to use the second method and don't own a scanner at home, you can check out the numerous scanning apps available for smartphones.

**Problem 1:**

Use induction to prove that

$$\sum_{k=1}^n k(k!) = (n+1)!-1.$$

**Solution:**

Proof: We proceed by induction on $$n$$.

When $$n=1$$, this says $$1(1)! = 2!-1$$, which is clearly true.

Let $$m\geq 0$$.
As an inductive assumption, suppose that the statement of the theorem holds for $$n=m$$.
In other words,

$$\sum_{k=1}^n k(k!) = (n+1)!-1.$$

Then for $$n = m+1$$ we calculate

$$
\begin{align*}
\sum_{k=1}^{m+1} k(k!)
  &= \sum_{k=1}^{m} k(k!) + (m+1)((m+1)!)\\
  &= (m+1)!-1 + (m+1)((m+1)!)\\
  &= -1 + (m+2)((m+1)!) = (m+2)! - 1.
\end{align*}
$$

Thus by the Principle of Induction, the statement holds for all $$n\geq 1$$.

**Problem 2:**

Prove that if $$1+a>0$$ then for all $$n\geq 1$$ 

$$(1 + a)^n\geq 1+na.$$

**Solution:**

This problem can be a bit tricky, since $$a$$ could potentially be negative.

Proof: To prove this, we will use strong induction.

First note that if $$n=1$$, the statement says $$1+a\geq 1+a$$, which is obviously true.

Let $$m\geq 1$$.
As an inductive assumption, suppose that the theorem holds for all $$1\leq n\leq m$$.

Then for $$n=m+1$$, we have that

$$(1+a)^{n+1} = (1+a)^{n-1}(1+a)^2.$$

Now using our inductive assumption, $$(1+a)^{n-1}\geq 1 + (n-1)a$$.
Therefore we have

$$
\begin{align*}
(1+a)^{n+1}
  & \geq (1 + (n-1)a)(1+a)^2\\
  & = 1 + (n-1)a + 2a + (n-1)a^2 + a^2 + (n-1)a^3\\
  & = 1 + (n+1)a + (n-1)a^2(1+a) + a^2\\
\end{align*}
$$

Since $$1+a > 0$$, this last expression is $$1+(n+1)a$$ plus a positive number.
Therefore

$$(1+a)^{n+1}\geq 1+(n+1)a.$$

Thus by the Principle of Induction, the statement holds for all $$n\geq 1$$.

**Problem 3:**

Kelly collects colorful sea shells on the beach, which she separates into bags to sell.
In her experience, as long as she collects at least $$12$$ shells, she is able
to separate them into bags, each of which contains $$4$$ or $$5$$ shells, with
no shells left over afterward.
Use strong induction to prove that this will always be true.

**Solution:**

Proof: To prove this, we will use strong induction on the number $$n$$ of shells.

First note the following.
* if we have $$12$$ shells, we can make three bags of $$4$$;
* if we have $$13$$ shells, we can make two bags of $$4$$ and one bag of $$5$$;
* if we have $$14$$ shells, we can make one bag of $$4$$ and two bags of $$5$$;
* if we have $$15$$ shells, we can make three bags of $$5$$.

Let $$m\geq 15$$.  As an inductive assumption, suppose that for any number $$n$$ of shells with $$12\leq n\leq m$$, we can separate our shells in to a collection of bags with $$4$$ and $$5$$, without any left over.

Suppose then we collect $$m+1$$ shells.
Then we can make $$1$$ bag of $$4$$ shells and still have $$m-3$$ shells left over.
Since $$m-3\geq 12$$ and $$m-3\leq m$$, our inductive assumption tells us this $$m-3$$ shells can be fit into an appropriate collection of bags.
Thus the whole collection of $$m+1$$ shells can be separated into a whole number of bags containing $$4$$ or $$5$$ shells.

Thus by the Principle of Induction, the statement holds for all $$n\geq 12$$.

Remark: it was important that we proved the first *four* cases, since otherwise $$m-3$$ could have been less than $$12$$, causing problems!

**Problem 4:** 

Let $$n\geq k\geq 0$$ be integers.
Prove the following facts about binomial coefficients.

* (A) $$\sum_{k=0}^n\binom{n}{k} = 2^n.$$
* (B) $$\sum_{k=0}^n(-1)^k\binom{n}{k} = 0.$$
* (C) $$\sum_{k=0}^n k\binom{n}{k} = n2^{n-1}.$$

**Solution:**

* (A) By the Binomial Theorem

$$2^n = (1+1)^n = \sum_{k=0}^n\binom{n}{k}1^k1^{n-k} = \sum_{k=0}^n\binom{n}{k}.$$

* (B) By the Binomial Theorem

$$0^n = (-1+1)^n = \sum_{k=0}^n\binom{n}{k}(-1)^k1^{n-k} = \sum_{k=0}^n\binom{n}{k}(-1)^k.$$

* (C) By the Binomial Theorem

$$(x+1)^n = \sum_{k=0}^n\binom{n}{k}x^k1^{n-k} = \sum_{k=0}^n\binom{n}{k}x^k.$$

Now if we take the derivative of both sids with respect to $$x$$, we find

$$n(x+1)^{n-1} = \sum_{k=0}^n\binom{n}{k}kx^{k-1}.$$

Plugging in $$x=1$$, this gives

$$n2^{n-1} = \sum_{k=0}^n\binom{n}{k}k.$$

**Problem 5:** 

Recall the $$n$$'th **triangle number** is 

$$t_n = \frac{n(n+1)}{2}.$$

* (A) Prove Aryabhata's formula (circa 500 A.D.)

$$t_1 + t_2 + t_3 + \dots + t_n = \frac{n(n+1)(n+2)}{6},\quad n\geq 1.$$

* (B) Prove that for all $$n\geq 1$$,

$$\frac{1}{t_1}+\frac{1}{t_2}+\dots+\frac{1}{t_n} < 2.$$

**Solution:**

* (A) This can easily be proved by induction.  However, maybe we are too cool
for induction and want to do it in as incredible a way as we can.  Let's do it.

First, let's remember the most important sum you will ever know: the **geometric sum**:

$$\sum_{k=0}^{n+1} x^k = \frac{x^{n+2}-1}{x-1}.$$

Clearing the denominator, this says

$$(x-1)\sum_{k=0} x^k = x^{n+2}-1.$$

Now take the third derivative of both sides

$$3\sum_{k=2}^{n+1} k(k-1)x^{k-1} + (x-1)\sum_{k=0}^n k(k-1)(k-2)x^{k-3} = (n+2)(n+1)nx^{n-2}.$$

Evaluating at $$x = 1$$, this says

$$3\sum_{k=2}^{n+1} k(k-1) = (n+2)(n+1)n.$$

Remembering our formula for the triangular numbers, we know $$k(k-1) = 2t_{k-1}$$ and therefore

$$6\sum_{k=2}^{n+1} t_{k-1} = (n+2)(n+1)n.$$

This is exactly what we wanted to prove.

* (B) Again, we can easily prove this with induction.  Alternatively, we can come up with the following slick solutoin.  The beautiful trick to this problem is to realize

$$\frac{1}{t_n} = \frac{2}{n(n+1)} = \frac{2}{n}-\frac{2}{n+1}.$$

Therefore the sum is **telescoping**:

$$
\begin{align*}
\sum_{k=1}^n \frac{1}{t_k}
  & = \sum_{k=1}^n \left(\frac{2}{k}-\frac{2}{k+1}\right)\\
  & = \sum_{k=1}^n \frac{2}{k} - \sum_{k=1}^n\frac{2}{k+1}\\
  & = \frac{2}{1} + \sum_{k=2}^n \frac{2}{k} - \sum_{k=1}^{n-1}\frac{2}{k+1} - \frac{2}{n+1}\\
  & = \frac{2}{1} + \sum_{k=2}^n \frac{2}{k} - \sum_{k=2}^{n}\frac{2}{k} - \frac{2}{n+1}\\
  & = \frac{2}{1} - \frac{2}{n+1} < 2.
\end{align*}.$$



