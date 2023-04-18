---
layout: page
title: Practice Exam 3 Solutions
permalink: /exams/practice-exam3-soln
---

Solve each of the following problems.
If the problem asks for a proof, be sure to carefully justify your work, including any theorems from class.

Note: you may NOT use a theorem or result from class to prove something when it makes the problem entirely trivial.  If you are unsure whether a particular theorem or result is allowed, just ask!

## Problem 1 (True or False)
For each of the following, write TRUE if the statement is true and FALSE if the statement is false.  NO explanation is needed.
Here $$n$$ is an arbitrary positive integer.

a) If $$x^2\equiv 1\mod n$$ then $$x\equiv \pm 1$$ mod $$n$$.

False!  For example if $$n=8$$, then $$x=3$$ satisfies $$x^2\equiv 1$$.

b) $$\phi(9)=\phi(3)\phi(3) = (3-1)(3-1) = 4$$.

False!  $$\phi(9) = \phi(3^2) = 3^2-3 = 6$$.

c) The Mobius function is the Dirichlet inverse of the constant function $$f(x)=1$$.

True!  This is how we defined it.

d) For any integer $$a$$, $$a^{\phi(n)}\equiv 1\mod n$$

False!  We need $$\gcd(a,n) = 1$$.

e) The value of $$\mu(90)$$ is $$1$$

False!  Since $$90$$ is divisible by $$3^2$$, $$\mu(90) = 0$$.

## Problem 2

a) State Gauss's Theorem and the Mobius Inversion of Gauss's Theorem.

Gauss's Theorem: Let $$n>1$ be an integer.  Then $$n =\sum_{d\mid n}\phi(d).$$

b) Write down all integers $$n$$ with $$\phi(n) = 4$$.

If $$n = p_1^{k_1}p_2^{k_2}\dots p_n^{k_n}$$, then 

$$\phi(n) = (p_1^{k_1}-p_1^{k_1-1}) (p_2^{k_2}-p_2^{k_2-1}) (p_r^{k_r}-p_r^{k_r-1})$$

For this product to be $$4$$, none of the $$p_k$$'s can be larger than $$5$$.
Also the powers of $$3$$ and $$5$$ are at most $$1$$.
Therefore $$n = 2^3, 2^2\cdot 3, 5, 2\cdot 5$$.

c) State the definition of an arithmetic function $$f(n)$$ being multiplicative.

A function $$f(n)$$ is multiplicative if and only if $$f(ab) = f(a)f(b)$$ for all positive integers $$a,b$$ which are relatively prime.

## Problem 3

Determine the value of each of the following sums.

a) $$\sum_{d\mid 1000} d$$ 

This is the sum of the divisors of $$1000$$, so the answer is

$$\sigma(1000) = \sigma(2^3\cdot 5^3) = \sigma(2^3)\sigma(5^3) = \frac{2^4-1}{2-1}\frac{5^4-1}{5-1} = 16\cdot 156 = 2496$$

b) $$\sum_{d\mid 1000} \mu(d)$$

Since $$\mu$$ is the inverse of the constant function, the result is

$$(\mathbf{1}\cdot \mu)(1000) = \varepsilon(1000) = 0.$$

c) $$\sum_{d\mid 1000} d\mu\left(\frac{n}{d}\right)$$

By the Mobius Inversion of Gauss's Theorem, this is the same as

$$\phi(1000) = \phi(2^3\cdot 5^3) = (2^3-2^2)(5^3-5^2) = 4\cdot 100 = 400.$$

## Problem 4

Find all solution of the following equations

a) Calculate $$\phi(576)$$

We calculate 

$$\phi(576) = \phi(2^6\cdot 3^2) = (2^6-2^5)(3^2-3) = 32\cdot 6 = 192.$$

b) Determine the order of $$3$$ modulo $$301$$.

Let $$k$$ be the order of $$3$$ modulo $$301$$.

Note that $$301 = 7\cdot 43$$.
Fermat's Little Theorem tells us $$3^{42}\equiv 1\mod 43$$ and $$3^6\equiv 1\mod 7$$.  Since $$42$$ is a multiple of $$6$$, this means $$3^{42}\equiv 1\mod 7$$.  Combining thes two facts, we get $$3^{42}\equiv 1\mod 301$$.  Thus the order of $$k$$ modulo $$301$$ divides $$42$$.

Now since $$3^k\equiv 1\mod  301$$, we have $$3^k\equiv 1\mod 7$$.  The order of $$3$$ modulo $$7$$ is $$6$$, so therefore $$k$$ must be a multiple of $$6$$.
The only divisors of $$42$$ which are multiples of $$6$$ are $$6$$ and $$42$$.  Since $$3^6$$ is not equivalent to $$1$$ mod $$301$$, we conclude that the order of $$3$$ must be $$42$$.

## Problem 5

Suppose that $$p$$ and $$q$$ are two distinct odd integers.
Prove that there is no primitive root modulo $$pq$$.

**Proof:**

Let $$a$$ be an integer and $$d=\gcd(p-1,q-1)$$.
Note that $$d\geq 2$$ because $$p$$ and $$q$$ are odd.

By Fermat's Little Theorem $$a^{p-1}\equiv 1\mod p$$ and $$a^{q-1}\equiv 1\mod q$$.
Therefore we have two identitis

$$a^{(p-1)(q-1)/d} = (a^{p-1})^{(q-1)/d}\equiv 1\mod p,$$

$$a^{(p-1)(q-1)/d} = (a^{q-1})^{(p-1)/d}\equiv 1\mod q.$$

Putting these together, we get

$$a^{(p-1)(q-1)/d}\equiv 1\mod pq.$$

This implies the order of $$a$$ divides $$(p-1)(q-1)/d < (p-1)(q-1) = \phi(pq)$$.
Thus $$a$$ cannot be primitive.  Since $$a$$ was arbitrary, this completes the proof.


## Problem 6

Find all integers $$n$$ satisfying

$$\sum_{d\mid n} \mu(d)\phi(d) = 2$$.

**Solution:**

We know that for $$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$ 

$$\sum_{d\mid n} \mu(d)\phi(d) = (2-p_1)(2-p_2)\dots (2-p_r)$$

Suppose that $$n$$ satisfies the statement.  Then

$$2 = (2-p_1)(2-p_2)\dots (2-p_r)$$.

This implies $$2$$ divides $$2-p_j$$ for some $$j$$, forcing $$p_j=2$$.  However, this makes the right hand side above $$0$$, a contradiction.  Therefore no values of $$n$$ make this possible.

## Problem 7

Consider the prime number $$p=2011$$.

a) How many integers $$x$$ are there with $$1\leq x  < p$$ whose order is $$2010$$?

Since $$2011$$ is prime, then answer is

$$\phi(2010) = \phi(2\cdot 3\cdot 5\cdot 67) = 1\cdot 2\cdot 4\cdot 66 = 528.$$

b) How many integers $$x$$ are there with $$1\leq x  < p$$ whose order is $$7$$?

Since $$7$$ doesn't divide $$2010$$, there are none.

c) How many integers $$x$$ are there with $$1\leq x  < p$$ whose order is $$10$$?

Since $$10$$ divides $$2010$$ and $$2011$$ is prime, there are

$$\phi(10) = \phi(2\cdot 5) = 1\cdot 4 = 4.$$

d) Given that $$3$$ is a primitive root of $$2011$$, find (up to congruence modulo $$2011$$) all solutions of the equation

$$x^{10}\equiv 1\mod 2011.$$

To get an element of order $$10$$, we take our primitive root $$3$$ and raise it to the power of $$2010/10 = 201$$.  Thus $$3^{201}$$ has order $$10$$.
To get three more elements of order $$10$$, we just need to raise the number $$3^{201}$$ to powers which are relatively prime to $$10$$, ie. to the power of $$3,7,$$ and $$9$$.  This gives us the four elements

$$3^{201},\quad 3^{201\cdot 3},\quad 3^{201\cdot 7},\quad 3^{201\cdot 9}.$$

All of these are incongruent modulo $$2011$$ and have order $$10$$ modulo $$2011$$.

However, the equation itself has more solutions.  In fact, we know that $$x^{d}-1\equiv 0\mod p$$ should have exactly $$d$$ solutions as long as $$d\mid (p-1)$$.
The solutions in general are $$x^{201 j}$$ for $$0\leq j < 9$$.

e) Given that $$3$$ is a primitive root of $$2011$$, find (up to congruence modulo $$2011$$) all integers whose order is $$10$$.

There should be $$\phi(10) = 4$$ solutions.  They are presented in  the solution of part (d).
