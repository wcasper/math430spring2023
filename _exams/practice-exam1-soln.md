---
layout: page
title: Practice Exam 1 Solutions
permalink: /exams/practice-exam1-soln
---

Solve each of the following problems.
If the problem asks for a proof, be sure to carefully justify your work, including any theorems from class.

Note: you may NOT use a theorem or result from class to prove something when it makes the problem entirely trivial.  If you are unsure whether a particular theorem or result is allowed, just ask!

## Problem 1 (True or False)
For each of the following, write TRUE if the statement is true and FALSE if the statement is false.  NO explanation is needed.

a) Any integer can be expressed in the form $$4j + 5k$$ for some integers $$j$$ and $$k$$

**TRUE**

b) The Well-Ordering Principle is equivalent to the Axiom of Induction

**TRUE**

c) Every integer is divisible by $$0$$

**FALSE**

d) $$\gcd(-33,-21) = -3$$

**FALSE**

e) $$(15-6q,6) = 3$$ for any integer $$q$$

**TRUE**

## Problem 2

a) State the Well-Ordering Principle

**Solution:**  The Well-Ordering Principle says that every set of non-negative integers has a least element.

b) State the Division Algorithm

**Solution:**  The Divison Algorithm says that for any integers $$a$$ and $$b$$ with $$b>0$$ there exists integers $$q$$ and $$r$$ satisfying

$$a = qb + r,\quad\text{with}\ \ 0\leq r < b.$$

c) Let $$a$$ and $$b$$ be integers.  Write the definition of the greatest common divisor of $$a$$ and $$b$$.

**Solution:** The greatest common divisor of $$a$$ and $$b$$ is an integer $$d$$ which divides both $$a$$ and $$b$$ and with the property that if $$c$$ divides both $$a$$ and $$b$$ also, then $$c \leq d$$.

## Problem 3

a) Use the Euclidean Algorithm to calculate the greatest common divisor of $$851$$ and $$222$$.

**Solution:**

$$\begin{align*}
851 & = 3\cdot 222 + 185\\
222 & = 1\cdot 185 + 37\\
185 & = 5\cdot 37 + 0
\end{align*}$$

Therefore $$\gcd(851,222) = 37$$.

b) Write the greatest common divisor from part $$(a)$$ as an integer linear combination of $$851$$ and $$222$$.

From the work of (a), we calculate

$$\begin{align*}
37 & = 222-185\\
   & = 222-(851-3\cdot 222)\\
   & = 5\cdot 222 + (-1)\cdot 851
\end{align*}$$

## Problem 4

Prove that $$2^{2023}+1$$ will be divisible by $$3$$.

**Solution:**

We can write

$$\begin{align*}
2^{2023}+1
 & = (3-1)^{2023} + 1\\
 & = \sum_{k=0}^{2023}\binom{2023}{k}3^k(-1)^{2023-k} + 1\\
 & = -1 + \sum_{k=1}^{2023}\binom{2023}{k}3^k(-1)^{2023-k} + 1\\
 & = \sum_{k=1}^{2023}\binom{2023}{k}3^k(-1)^{2023-k}
\end{align*}$$.

Every term in this last sum is divisible by $$3$$, so $$2^{2023}+1$$ is divisible by $$3$$.

## Problem 5

Use induction to prove $$\frac{(2n)!}{n!2^n}$$ is an integer for all $$n\geq 0$$.

**Solution:**

Proof: We will prove this using induction.

When $$n=0$$, $$\frac{(2n)!}{n!2^n} = 1$$.

Let $$m\geq 0$$.
As an inductive assumption, suppose that $$\frac{(2m)!}{m!2^m}$$ is an integer.

Then we calculate,

$$\frac{(2(m+1))!}{(m+1)!2^{m+1}} = \frac{(2m+2)(2m+1)(2m)!}{m!2^m(m+1)2} = (2m+1)\frac{(2m)!}{m!2^m}.$$

By our inductive assumption, the right hand side is a product of two integers and therefore an integer.

Thus by PMI, the statement is true for all $$n\geq 0$$.

## Problem 6

Let $$a$$ be an integer.
Prove that $$3a^2+2$$ cannot be a perfect square.

[Hint: Assume $$3a^2+2=k^2$$ and apply the Division Algorithm to $$k$$ and $$3$$.]

**Solution:**

Proof:  We will use proof by contradiction.

Assume that $$3a^2+2=k^2$$ for some integer $$k$$.
By the division algorithm, we can write $$k = 3q + r$$ for $$0\leq r < 3$$.
Then $$k^2 = (3q + r)^2 = 9q^2 + 6qr + r^2$$, so 

$$3a^2 + 2 = 9q^2+6qr + r^2.$$

Putting all the things which are obviously divisible by $$3$$ on the left-hand side, this says

$$3a^2 - 9q^2-6qr = r^2-2.$$

Thus $$r^2-2$$ must be divisible by $$3$$.  However, since $$r=0$$ or $$r=1$$, this is impossible.

This is a contradiction, so $$3a^2+2$$ cannot be a perfect square.

## Problem 7

Let $$F_1, F_2,\dots$$ be the Fibonacci numbers.  Prove that the greatest common divisor of $$F_k$$ and $$F_{k+1}$$ is always $$1$$.

**Solution:**

Proof:  We will prove this using induction.

If $$k=1$$, this says that the GCD of $$1$$ and $$1$$ is $$1$$, which is obvious.

Let $$m\geq 1$$.  As an inductive assumption, suppose that $$\gcd(F_{m},F_{m+1}) = 1$$.

Then

$$\gcd(F_{m+1},F_{m+2}) = \gcd(F_{m+1},F_{m}+F_{m+1}).$$

Now if $$a$$ and $$b$$ are any integers, then $$d$$ divides both $$a$$ and $$b$$ if and only if $$d$$ divides both $$a$$ and $$a+b$$.
Consequently $$\gcd(a,b) = \gcd(a,a+b)$$.

Applying this to the case $$a = F_{m+1}$$ and $$b =F_{m}$$, our inductive assumption tells us

$$\gcd(F_{m+1},F_{m+2}) = \gcd(F_{m+1},F_{m}+F_{m+1}) = \gcd(F_{m+1},F_m) = 1.$$

Thus by PMI, the statement is true for all $$k\geq 1$$.

