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

Each of these functions has the property that they *multiplicative*.

**Definition:** A number-theoretic function $$f(n)$$ is called multiplicative if

$$f(mn) = f(m)f(n), \text{whenever}\ \gcd(m,n)=1.$$

The fact that $$\mu(n)$$ is multiplicative is kind of obvious.
However, the multiplicativity of $$\sigma$$ and $$\tau$$ is a little less clear and will be proved below.

## Identities for special number-theoretic functions

These special number-theoretic functions have some very curious properties and appear in many examples of striking identities.
Many of these identities will involve taking a sum or a product over the number of divisors, so we establish the following notation.

**Notation:** We will write $$\sum_{d\mid n} f(d)$$ and $$\prod_{d\mid n} f(d)$$ to mean the sum / product of $$f(d)$$ as $$d$$ ranges over all divisors of $$n$$.

For example

$$\begin{align}
\sum_{d\mid 6} f(d) &= f(1) + f(2) + f(3) + f(6)\\
\prod_{d\mid 6} f(d) &= f(1)f(2)f(3)f(6)
\end{align}$$
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

$$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$

for distinct primes $$p_1,p_2,\dots p_r$$.

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

**Example:**  Consider the integer $$n=320=2^6\cdot 5$$.  Using the above equations, we have

$$\tau(320) = 7\cdot 2 = 14,$$

$$\sigma(320) = \frac{2^7-1}{2-1}\frac{5^2-1}{5-1} = 128\cdot 6 = 768.$$

As another example, we can consider the product of all the divisors of an integer $$n$$.

As an immediate consequence of this, we get that $$\tau$$ and $$\sigma$$ are multiplicative.

**Theorem:**  The functions $$\tau$$ and $$\sigma$$ are multiplicative.

**Proof:** Suppose that $$m$$ and $$n$$ are relatively prime and

$$m = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r},\quad n = q_1^{\ell_1}q_2^{\ell_2}\dots q_r^{\ell_s}.$$

Then $$p_i\neq q_j$$ for all $$r$$ and $$s$$.
Consequently

$$mn = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}q_1^{\ell_1}q_2^{\ell_2}\dots q_r^{\ell_s}$$

is the factorization of $$mn$$ into powers of distinct primes.
The fact that $$\sigma(mn) = \sigma(m)\sigma(n)$$ and $$\tau(mn) = \tau(m)\tau(n)$$ then follows immediately from the previous theorem.

:black_square_button:


**Theorem:** Let $$n$$ be an integer.  Then

$$\prod_{d\mid n} d = n^{\tau(n)/2}.$$

**Proof:**

The proof of this is reminiscent of Gauss's derivation of the sum of the first $$n$$ integers.

Let $$m = \tau(n)$$ and $$1=d_1 < d_2 < \dots < d_m = n$$ be the divisors of $$n$$, in increasing order.
We can notice that for each $$k$$, $$n/d_k$$ is a divisor of $$n$$, and in fact $$d_{n-k} = n/d_k$$.
Thus

$$\begin{align}
\prod_{d\mid n} d &= d_1d_2d_3\dots d_m\\
\prod_{d\mid n} d &= d_md_{m-1}d_{m-2}\dots d_1.
\end{align}$$

Multipliying these together, we get

$$\left(\prod_{d\mid n} d\right)^2 = (d_1d_m)(d_2d_{m-1})(d_3d_{m-2})\dots (d_md_1) = n^m.$$

The statement of the theorem follows immediately.

:black_square_button:








