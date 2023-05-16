---
layout: page
title: Practice Final Solutions
permalink: /exams/practice-final-soln
---

Solve each of the following problems.
If the problem asks for a proof, be sure to carefully justify your work, including any theorems from class.

Note: you may NOT use a theorem or result from class to prove something when it makes the problem entirely trivial.  If you are unsure whether a particular theorem or result is allowed, just ask!

## Problem 1 (True or False)
For each of the following, write TRUE if the statement is true and FALSE if the statement is false.  NO explanation is needed.
Here $$n$$ is an arbitrary positive integer.

a) If $$f(n)$$ is multiplicative and $$f(3) = 2$$, then $$f(9)$$ must be $$4$$.

FALSE!  Multiplicativity guarantees $$f(ab) = f(a)f(b)$$ only when $$a,b$$ are relatively prime.

b) For any odd prime $$p$$, the number of quadratic residues is the same as the number of quadratic nonresidues.

TRUE!

c) $$99!$$ is equivalent to $$1$$ modulo $$101$$

TRUE! Think about Wilson's Theorem

d)  8911 = 7 · 19 · 67 is a Carmichael number

TRUE!  Just check $$n$$ is square-free and $$p-1$$ to divide $$n-1$$ for all primes $$p\mid n$$.

e)  If $$1234x6789$$ is divisible by $$9$$, then $$x=0$$

FALSE!  For the number to be divisible by $$9$$ the sum of its digits must be divisible by $$9$$ also.  So $$x$$ would have to be $$5$$.

## Problem 2

a) State Gauss's Lemma

Gauss's Lemma says that if $$p$$ is an odd prime and $$\gcd(a,p)=1$$ then $$(a/p)= (-1)^n$$ for $$n$$ the number of elements $$a,2a,\dots,((p-1)/2)a$$ whose positive remainders modulo $$p$$ are greater than $$p/2$$.

b) State Gauss's Theorem

Gauss's Theorem says

$$\sum_{d\mid n} \phi(d) = n.$$

c) State the definition of a quadratic residue mod $$n$$

A number $$a$$ is a quadratic residue modulo $$n$$ if $$a$$ is equivalent to $$k^2$$ for some integer $$k$$ modulo $$n$$.

d) State the definition of a composite number

A number $$a$$ is composite if it can be written as a product $$a = bc$$ for two numbers $$b$$ and $$c$$ different from $$\pm 1$$.

e) State the Quadratic Reciprocity Law

The quadratic reciprocity law says that if $$q$$ and $$p$$ are distinct odd primes $$(p/q)(q/p) = (-1)^{\frac{p-1}{2}\frac{q-1}{2}}$$.

f) Define the order of an integer $$x$$ modulo $$n$$.  What has to be true about $$x$$ and $$n$$ for this to make sense?

The order of an integer $$x$$ is the smallest positive integer $$k$$ satisfying $$x^k\equiv 1\mod n$$.  For this to make sense, we require that $$\gcd(a,n) = 1$$.

## Problem 3

a) Use the Euclidean algorithm to find all integer solution to

$$37x + 41y = -3.$$

Carefully show your work!

b) Find all values of $$x$$ with $$37x\equiv 38$$ mod $$41$$.


**Solution:**

a) Using the Euclidean algorithm

$$\begin{align}
41 &= 37 + 4\\
37 &= 9\cdot 4 + 1
\end{align}$$

Therefore $$\gcd(37,41) = 1$$ and 

$$1 = 37 - 9\cdot 4 = 37 - 9(41-37) = 10\cdot 37 - 9\cdot 41.$$

It follows that any integer solution is given by

$$x = -30 + 41 k,\quad y = 27-37k$$

for some integer $$k\in\mathbb{Z}$$.

b) Notice that $$38\equiv -3\mod 41$$, therefore the solutions are given by

$$x = -30 + 41k,\quad k\in\mathbb{Z}.$$

## Problem 4

Suppose that $$f(x)$$ and $$g(x)$$ are two multiplicative arithmetic functions whose first few values are given in the table below.

$$\begin{array}{c|c|c|c|c|c|c|c}
x    & 1 & 2 & 3 & 4 & 5 & 6 & 7 \\\hline
f(x) & 1 & 3 & 2 & 7 & 5 & 6 & 4 \\\hline
g(x) & 1 & 1 & 7 & 9 & 2 & 7 & 1
\end{array}
$$

a) Find the value of $$f(420)$$.

b) Suppose that $$h(x)$$ is a new function which you know satisfies

$$f(n) = \sum_{d\mid n} h(d).$$

Find the value of $$h(60)$$.

c) Determine the value of the Dirichlet convolution

$$(f * g)(420)$$

[Hint: to make it easier, use the fact that $$f * g$$ is multiplicative]


435
 1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30, 60.
60,30,20,15,12,10,  6,  5,  4,  3,  2,  1

**Solution:**

a) We calculate

$$f(420) = f(4)f(3)f(5)f(7) = 7\cdot 2\cdot 5\cdot 4 = 280.$$

b) We use Mobius Inversion to see $$h(n) = \sum_{d\mid n}f(d)\mu(n/d)$$. Thus

$$h(60) = f(60) - f(30) - f(20) - f(12) + f(10) + f(6) + f(4) - f(2)$$

Now using multiplicativity

$$h(60) = f(4)f(3)f(5) - f(2)f(3)f(5) - f(4)f(5) - f(4)f(3) + f(2)f(5) + f(6) + f(4) - f(2)$$

In the end, we obtain

$$h(60) = 70-30 - 35 - 14 + 15 + 6 + 7 - 3 = 16.$$

c) 

Remember $$(f* g)(n) = \sum_{d\mid n} f(d)g(n/d)$$.

We can put together a table of values

$$\begin{array}{c|c|c|c|c|c|c|c}
x         & 1 & 2 & 3 & 4  & 5 &  6 & 7 \\\hline
(f* g)(x) & 1 & 4 & 9 & 19 & 7 & 36 & 5 \\\hline
\end{array}
$$

Therefore

$$(f* g)(420) = (f* g)(4)(f* g)(3)(f* g)(5)(f* g)(7)= 19\cdot 9\cdot 7 \cdot 5 = 5985.$$

## Problem 5

Find a solution of the system of linear congruences

$$\begin{align}
x&\equiv -1 \mod 7\\
x&\equiv 3 \mod 15\\
x&\equiv 5 \mod 8
\end{align}$$

**Solution:**

By CRT, we know a solution exists (all the moduli are relatively prime).
We look for a solution of the form

$$x = a\cdot 8\cdot 15 + b\cdot 7\cdot 8 + c\cdot 7\cdot 15.$$

Reducing this mod $$7$$, we see that $$a\equiv -1\mod 7$$.
Reducing this mod $$15$$, we see $$11b\equiv 3\mod 15$$.
Reducing this mod $$8$$, we see $$c\equiv 5\mod 8.$$

Therefore a solution is given by $$a=-1,b=3$$ and $$c=5$$, ie. $$x = 573$$.  This solution is unique up to equivalence mod $$7\cdot 15\cdot 8 = 840$$.

## Problem 6

a) Find, the remainder when $$3^{1442}$$ is divided by $$700$$.

b) Give a factor of $$2^{88}+1$$.  Explain.

**Solution:**

a) We calculate $$\phi(700) = 240$$ and $$1440 = 240\cdot 6$$.  Therefore by Euler's Theorem

$$3^{1442} = 3^2\cdot (3^{240})^6\equiv 3^2\cdot 1^6 = 9\mod 700.$$

It follows that the remainder is $$9$$.

b) We can write

$$2^{88}+1 = -((-2^8)^{11}-1).$$

Now recalling that $$x^n-1 = (x-1)(x^{n-1} + x^{n-2} + \dots + x + 1)$$, we see:

$$2^{88}+1 = -((-2^8)-1)((-2^8)^{10} + (-2^8)^9 + \dots + (-2^8) + 1).$$

In particular, one factor is $$2^8+1 = 257$$.


## Problem 7

a) Given that

$$F(n) = \sum_{d\mid n} \mu(d)\sigma(d)^2$$

find $$F(40)$$

b) Given that

$$\tau(n)^2 = \sum_{d\mid n}g(d)$$

find $$g(7^3)$$.


**Solution:**

a) Since $$40 = 8\cdot 5$$, we have that

$$F(40) = (1-\sigma(2)^2)(1-\sigma(5)^2) = (1-3^2)(1-6^2) = 280.$$

b) By Mobius inversion

$$g(n) = \sum_{d\mid n}\mu(d)\tau(n/d)^2.$$

Using the explicit value of the Mobius function:

$$g(7^3) = \sum_{d\mid 7^3}\mu(d)\tau(7^3/d)^2 = \tau(7^3)^2 - \mu(7)\tau(7^2)^2 = 4^2-3^2 = 7.$$

## Problem 8

Let $$F_1,F_2,F_3,\dots$$ be the Fibonacci sequence.  Prove that

$$F_1 + F_3 + F_5 + \dots + F_{2n-1} = F_{2n}.$$


**Solution 1:**

We proceed by induction on $$n$$.

Since $$F_1=F_2$$, the statement is true for $$n=1$$.

As an inductive assumption, suppose that  for somee intger $$k\geq 1$$ we have

$$F_1 + F_3 + F_5 + \dots + F_{2k-1} = F_{2k}.$$

Then for $$n=k+1$$, we calculate

$$F_1 + F_3 + F_5 + \dots + F_{2k+1} = F_{2k} + F_{2k+1} = F_{2k+2}.$$

Thus by the Principle of Induction, the theorem holds for all $$n$$.

**Solution 2:**

The Fibonacci sequence can be expressed in terms of the Golden ratio $$\varphi = \frac{1+\sqrt{5}}{2}$$ and its conjugate $$\psi = \frac{1-\sqrt{5}}{2}.$$

Specifically, we know:

$$F_n = \frac{\varphi^n-\psi^n}{\varphi-\psi}.$$

Now from geometric series, for any $$x$$ we have $$\sum_{k=1}^n x^{2k-1} = \frac{x^{2n}-1}{x(x^2-1)}.$$

Therefore 

$$\begin{align}
\sum_{k=1}^n F_{2k-1}
 & = \frac{1}{\varphi-\psi} \sum_{k=1}^n\varphi^{2k-1}-\psi^{2k-1}\\
 & = \frac{1}{\varphi-\psi}\left(\frac{\varphi^{2n}-1}{\varphi(\varphi^2-1)}-\frac{\psi^{2n}-1}{\psi(\psi^2-1)}\right)\\
 & = \frac{1}{\varphi-\psi}(\varphi^{2n}-\psi^{2n}) = F_{2n}.
 \end{align}$$

## Problem 9

Determine the value of each of the following Legendre symbols.

a) $$(-1/8675309)$$

b) $$(5/1307)$$

c) $$(461/773)$$


**Solution:**

a)  Since $$8675309$$ is equivalent to $$1$$ mod $$4$$, the value is 

b)  By Q.R.

$$(5/1307) = (1307/5) = (2/5) = (-1)^{(5^2-1)/8} = -1.$$

c) By Q.R.

$$(461/773) = (773/461) = (312/461) = (2^2/461)(2/461)(3/461)(13/461) = 1\cdot (-1)^{(461^2-1)/8}\cdot (461/3)(461/13)$$

Then since $$461 \equiv 2\mod 3$$ and $$461\equiv 6\mod 13$$,

$$(461/773) = -(2/3)(6/13) = (2/13)(3/13)= (-1)^{(13^2-1)/8}(13/3) = -(1/3) = -1.$$

## Problem 10

Suppose that $$p \geq 11$$ is a prime.

Show that there is a number $$n$$ with $$1\leq n \leq 10$$ such that both $$n$$ and $$n+1$$ are quadratic residues.

**Solution:**

Assume otherwise, ie. that for all $$n$$ between $$1$$ and $$10$$ either $$n$$ or $$n+1$$ is a quadratic nonresidue mod $$p$$.

Then since $$1,4,9$$ are all quadratic residues, $$2,3,5,$$ and $$10$$ must not be.  To summarize, we have the following table

$$\begin{array}{c|c|c|c|c|c|c|c}
a     & 1 & 2 & 3 & 4 & 5 & 6 & 7 & 8 & 9 & 10 \\\hline
(a/p) & 1 &-1 &-1 & 1 &-1 & ? & ? &-1 & 1 & -1 \\\hline
\end{array}
$$

However, since $$10=2\cdot 5$$, this says

$$-1 = (10/p) = (2/p)(5/p) = (-1)(-1).$$

This is a contradiction.

## Problem 11

Determine which of the following quadratic congruence equations are solvable 

a) $$3x^2+6x+5 = 0\mod 89$$

b) $$2x^2+5x-9 = 0\mod 101$$

**Solution:**

a) We just need to check if $$6^2-4\cdot 3\cdot 5 = -24$$ is a quadratic residue, ie. whether $$(-24/89)$$ is $$1$$ or $$-1$$.
We have

$$(-24/89) = (-1/89)(4/89)(2/89)(3/89) = 1\cdot 1\cdot (-1)^{(89^2-1)/8}(3/89) = (3/89) = (89/3) = (2/3) = -1.$$

Thus $$-24$$ is not a quadratic residue and the quadratic congruence has no solution.

b) Again, we want to know about $$25-4\cdot 2\cdot(-9) = 97$$.  We have that $$(97/101)=(-4/101) = (-1/101)(4/101) = 1$$.  Therefore the quadratic congruence has a solution.

## Problem 12

a) Prove

$$(5/p) = 1\quad\Leftrightarrow\quad p = 1,9,11,19\mod 20.$$

b)

$$(6/p) = 1\quad\Leftrightarrow\quad p = 1,5,19,23\mod 24.$$


**Solution:**

a) By Q.R. we have that $$(5/p) = (p/5)$$, which is $$1$$ if and only if $$p\equiv 1$$ or $$-1$$ modulo $$5$$, equivalently

$$p=1,4,6,9,11,14,16,19\mod 20.$$

However, since $$p$$ is odd, it's value must also be odd modulo $$20$$, so the only possibilities are $$1,9,11,$$ and $$19$$.

b)

By Q.R. we have $$(6/p) = (2/p)(3/p)$$.

Now

$$(2/p) = \left\lbrace\begin{array}{cc}1 & p\equiv \pm 1\mod 8\\ -1 & p\equiv \pm 3\mod 8\end{array}\right.

Also

$$(3/p) = \left\lbrace\begin{array}{cc}(p/3) & p\equiv 1\mod 4\\ -(p/3) & p\equiv -1\mod 4\end{array}\right.

and furthermore

$$(p/3) = \left\lbrace\begin{array}{cc}1 & p\equiv 1\mod 3\\ -1 & p\equiv -1\mod 3\end{array}\right.

Thus $$(6/p)$$ is positive if and only if one of the following sets of conditions is satisfied 

- $$p\equiv \pm 1\mod 8$$, $$p\equiv 1\mod 4$$, and $$p\equiv 1\mod 3$$

The numbers which satisfy this are equivalent to $$1$$ modulo both $$8$$ and $$3$$, ie. equivalent to $$1$$ modulo $$24$$.

- $$p\equiv \pm 1\mod 8$$, $$p\equiv-1\mod 4$$, and $$p\equiv-1\mod 3$$

The numbers which satisfy this are equivalent to $$-1$$ modulo both $$8$$ and $$3$$, ie. equivalent to $$-1$$ modulo $$24$$.

- $$p\equiv \pm 3\mod 8$$, $$p\equiv-1\mod 4$$, and $$p\equiv 1\mod 3$$

The numbers which satisfy this are equivalent to $$3$$ modulo $$8$$ and equivalent to $$1$$ modulo $$3$$, ie. equivalent to $$19$$ modulo $$24$$.

- $$p\equiv \pm 3\mod 8$$, $$p\equiv 1\mod 4$$, and $$p\equiv-1\mod 3$$

The numbers which satisfy this are equivalent to $$-3$$ modulo $$8$$ and equivalent to $$-1$$ modulo $$3$$, ie. equivalent to $$5$$ modulo $$24$$.

To summarize, $$(6/p)$$ is $$1$$ if and only if $$p$$ is congruent to $$1,5,19,$$ or $$23$$ mod $$24$$.



