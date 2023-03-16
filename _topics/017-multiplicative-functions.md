---
layout: page
title: Multiplicative functions
---


A **number-theoretic** or **arithmetic** function is any function whose domain is the set $$\mathbb N$$ of positive integers.
Some examples of particularly important number-theoretic funcions are
One particularly important example of a function is called a multiplicative function.

**Definition:** A number-theoretic function $$f(n)$$ is called multiplicative if

$$f(mn) = f(m)f(n), \text{whenever}\ \gcd(m,n)=1.$$

There are some very basic examples of multiplicative functions.

**Example:** The constant function $$f(n) = 1$$ is multiplicative.

**Example:** The identity function $$f(n) = n$$ is multiplicative.

More generally, the product of multiplicative functions will also be multiplicative.

To get more interesting examples of multiplicative functions, we first establish a convenient notation for sums and products over divisors.

**Notation:** We will write $$\sum_{d\mid n} f(d)$$ and $$\prod_{d\mid n} f(d)$$ to mean the sum / product of $$f(d)$$ as $$d$$ ranges over all divisors of $$n$$.

For example

$$\begin{align}
\sum_{d\mid 6} f(d) &= f(1) + f(2) + f(3) + f(6)\\
\prod_{d\mid 6} f(d) &= f(1)f(2)f(3)f(6)
\end{align}$$

With this notation in mind, we have the following theorem.

**Theorem:** Let $$f(n)$$ be a multiplicative function.  Then

$$F(n) = \sum_{d\mid n} f(d)$$

is also a multiplicative function.

**Proof:**

Suppose that $$m$$ and $$n$$ are relatively prime.  If $$a\mid m$$ and $$b\mid n$$ then $$ab\mid mn$$.  Conversely, suppose that $$d\mid mn$$.  Write $$d=p_1^{k_1}\dots p_r^{k_r}$$.  Then for each $$j$$, $$p_j$$ divides either $$m$$ or $$n$$, but not both.  Therefore we can write $$d = ab$$ where $$a = \prod_{j: p_j\mid m}p_j^{k_j}$$ and $$b = \prod_{j: p_j\mid n}p_j^{k_j}$$.  Thus

$$F(mn) = \sum_{d\mid mn} f(d) = \sum_{a\mid m}\sum_{b\mid n} f(ab) = \sum_{a\mid m}\sum_{b\mid n} f(a)f(b) = \left(\sum_{a\mid m}f(a)\right)\left(\sum_{b\mid n} f(b)\right) = F(m)F(n).$$

:black_square_button:

Using this, we can immediately get two very interesting examples of multiplicative functions

* The **number-of-divisors function** $$\tau$$ takes a positive integer $$n$$ and returns the number of positive divisors of $$n$$.

$$\tau(n) = \sum_{d\mid n} 1.$$

* The **sum-of-divisors function** $$\sigma$$ takes a positive integer $$n$$ and returns the sum of the positive divisors of $$n$$.

$$\sigma(n) = \sum_{d\mid n} d.$$

**Example:** The divisors of $$30$$ are $$1,2,3,5,6,10,15$$ and $$30$$.

$$\tau(30) = 8,\quad \sigma(30) = 1+2+3+5+6+10+15 = 42,\quad \mu(30) = 1.$$

## Identities for divisor functions

These special number-theoretic functions have some very curious properties and appear in many examples of striking identities.

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

Using this, we have the following theorem, giving us an explicit way to calculate the value of $$\tau(n)$$ and $$\sigma(n)$$, if we know the prime factorizations.

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

As another interesting identity, we can consider the product of all the divisors of an integer $$n$$.

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








