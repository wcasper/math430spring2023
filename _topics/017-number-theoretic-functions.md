---
layout: page
title: Number-theoretic functions
---


A **number-theoretic** or **arithmetic** function is any function whose domain is the set $$\mathbb N$$ of positive integers.
Some examples of particularly important number-theoretic funcions are

* The **number-of-divisors function** $$\tau$$ takes a positive integer $$n$$ and returns the number of positive divisors of $$n$$.
* The **sum-of-divisors function** $$\sigma$$ takes a positive integer $$n$$ and returns the sum of the positive divisors of $$n$$.
* The **Mobius function** $$\mu$$ takes a positive intger $$n$$ and returns

$$\mu(n) = \left\lbrace\begin{array}{cc}
1& \text{$n$ is square-free and has an even number of prime factors}\\
-1& \text{$n$ is square-free and has an odd number of prime factors}\\
0& \text{$n$ is divisible by the square of a prime}
\end{array}\right.$$

**Example:** The divisors of $$30$$ are $$1,2,3,5,6,10,15$$ and $$30$$.

$$\tau(30) = 8,\quad \sigma(30) = 1+2+3+5+6+10+15 = 42,\quad \mu(30) = 1.$$

These special number-theoretic functions have some very curious properties and appear in many examples of striking identities.
Many of these identities will involve taking a sum or a product over the number of divisors, so we establish the following notation.

**Notation:** We will write $$\sum_{d\mid n} f(d)$$ and $$\prod_{d\mid n} f(d)$$ to mean the sum / product of $$f(d)$$ as $$d$$ ranges over all divisors of $$n$$.

For example

$$\begin{align}
\sum_{d\mid 6} f(d) &= f(1) + f(2) + f(3) + f(6)\\
\prod_{d\mid 6} f(d) &= f(1)f(2)f(3)f(6)
\end{align}$$

## Identities for special number-theoretic functions
To start, we can get some very interesting expressions for $$\tau$$ and $$\sigma$$ in terms of the prime factorization of $$n$$.

**Theorem:**  Let $$n$$ be a positive integer with prime factorization

$$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$

for unique primes $$p_1,\dots,p_r$$.  Then the divisors of $$n$$ are exactly those of the form 

$$p_1^{a_1}p_2^{a_2}\dots p_r^{a_r},\quad\text{with}\ 0\leq a_j\leq k_j\ \text{for all }j.$$

**Proof:**

First, note that $$p_1^{a_1}p_2^{a_2}\dots p_r^{a_r}$$ is a divisor of $$n$$ because 

$$n = p_1^{a_1}p_2^{a_2}\dots p_r^{a_r}p_1^{k_1-a_1}p_2^{k_2-a_2}\dots p_r^{k_r-a_r}.$$

Conversely, suppose that $$b\mid n$$ is a positive divisor of $$n$$.
Then there is a positive integer $$c$$ with $$bc = n$$.
By the Fundamental Theorem of Arithmetic, both $$b$$ and $$c$$ have prime factorizations

$$b = u_1u_2\dots u_s,\quad\quad c = v_1v_2\dots v_t.$$

Therefore $$bc = u_1u_2\dots u_sv_1v_2\dots v_t$$ is a prime factorization of $$n$$.  Since prime factorizations are unique (up to order), each of the $$u_j$$'s must be one of the primes $$p_i$$.  Gathering similar powers of primes, we obtain $$b = p_1^{a_1}p_2^{a_2}\dots p_r^{a_r}$$ for some integers $$a_1,\dots,a_r$$ with $$0\leq a_j\leq k_j$$ for all $$j$$.

:black_square_button:

Using this, we have the following theorem.

**Theorem:**  Let $$n$$ be a positive integer with prime factorization

$$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}.$$

Then

$$\begin{align}
\tau(n)   &= (k_1+1)(k_2+1)\dots (k_r+1)\\
\sigma(n) &= \frac{p_1^{k_1+1}-1}{p_1-1}\frac{p_1^{k_2+1}-1}{p_2-1}\dots\frac{p_r^{k_r+1}-1}{p_r-1}
\end{align}$$

**Proof:**

Since each divisor is of the form $$p_1^{a_1}p_2^{a_2}\dots p_r^{a_r}$$, and $$a_j$$ can take values $$0\leq a_j\leq k_j$$ ($$k_j+1$$ possibilities), there are $$(k_1+1)(k_2+1)\dots (k_r+1)$$ divisors of $$n$$.

Furthermore, the sum of the divisors is

$$\begin{align}
\sigma(n)
  &= \sum_{a_1=0}^{k_1}\sum_{a_2=0}^{k_2}\dots\sum_{a_r=0}^{k_r}p_1^{a_1}p_2^{a_2}\dots p_r^{a_r}\\
  &= \left(\sum_{a_1=0}^{k_1}p_1^{a_1}\right)\left(\sum_{a_2=0}^{k_2}p_2^{a_2}\right)\dots\left(\sum_{a_r=0}^{k_r}p_r^{a_r}\right)\\
  &= \frac{p_1^{k_1+1}-1}{p_1-1}\frac{p_1^{k_2+1}-1}{p_2-1}\dots\frac{p_r^{k_r+1}-1}{p_r-1}
\end{align}$$

:black_square_button:





