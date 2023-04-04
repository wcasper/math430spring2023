---
layout: page
title: Euler's totent function
---

The usefulness of Fermat's Little Theorem is difficult to deny.
It helps us to understand exponents of large integers modulo a prime, and gives us an interesting necessary condition for primality, leading to further notions like pseudoprimes.
In other areas of mathematics not explored in this class, it provides us with an important function called the **Frobenius map**, which plays a pivotal role in our understanding of geometry and field theory in characteristic $$p$$.

The first actual published proof of Fermat's Little Theorem was *not* by Fermat.
Indeed, Fermat liked to keep his secrets, instead making incredible statements about numbers and leaving the rest of the mathematical community to puzzle out how he found them.
Instead, Euler provided the first proof of Fermat's Little Theorem in 1736.
Perhaps motivated by this fundamental imporance of this theorem, he was motivated to try to extend it to a theorem about composite residues.
He eventually succeeded 14 years later in 1760, using what is now referred to as Euler's totent function, one of the most important multiplicative functions in elementary number theory.


**Definition:** Eulers **totent function** or Euler's **phi function** is the number-theoretic function $$\phi$$ whose value at an integer $$n$$ is the number of positive integers less than $$n$$ which are relatively prime to $$n$$.

**Example:**  Here are some example values

* $$\phi(2) = 1$$ (only $$1$$ is relatively prime to $$2$$ and less than $$2$$)
* $$\phi(7) = 6$$ (all numbers between $$1$$ and $$6$$ are relatively prime with $$7$$)
* $$\phi(8) = 3$$ (all odd numbers are relatively prime to $$8$$)

In order to get a sense of the value of the totent function, we first evaluate it on powers of primes.

**Theorem:**  Let $$p$$ be a prime and $$k$$ be a positive integer.  Then

$$\varphi(p^k) = p^k-p^{k-1}.$$

**Proof:**

If $$\gcd(m,p^n)\neq 1$$ then $$m$$ must be a multiple of $$p$$.
There are $$p^{n-1}$$ positive multiples of $$p$$ less than or equal to $$p^n$$, so the remaining $$p^n-p^{n-1}$$ numbers must not be multiples of $$p$$ and therefore reelatively prime to $$p^n$$.
:black_square_button:


There is a fundamental relationship between the value of Euler's totent function at an integer and its divisors.

**Gauss's Theorem:**  Let $$n$$ be a positive integer.  Then

$$n = \sum_{d\mid n} \phi(d).$$

**Proof:**

For each $$d\mid n$$ let

$$A_d = \{x : \gcd(x,n) = d\}.$$

Then the sets $$A_d$$ as $$d$$ ranges through the divisors of $$n$$ form a partition of $$\{1,2,\dots, n\}$$, ie.

$$\bigcup_{d\mid n} A_d = \{1,2,\dots, n\}.$$

Hence in particular

$$\sum_{d\mid n} \lvert A_d\rvert = n.$$

Moreover, $$\gcd(x,n) = d$$ if and only if $$\gcd(x/d,n/d) = 1$$, and therefore

$$\{y: 1\leq y\leq n/d,\quad \gcd(y,n/d) = 1\} = \{x/d: x\in A_d\}.$$

In particular, $$\phi(n/d) = \lvert A_d\rvert.$$

Thus 

$$n = \sum_{d\mid n} \lvert A_d\rvert = \sum_{d\mid n} \varphi(n/d) = \sum_{d\mid n} \varphi(d).$$

:black_square_button:

As a consequence of this, we can see right away that the totent function is multiplicative.

**Theorem:** Euler's totent function $$\varphi$$ is multiplicative and satisfies

$$\varphi(n) = n\sum_{d\mid n} \frac{\mu(d)}{d}.$$

**Proof:**

From the previous theorem, we know that the Dirichlet convolution of Euler's totent function with the constant function $$1$$ is the identity function

$$\text{id}(n) = n = \sum_{d\mid n} \varphi(d) = (\varphi * 1)(n).$$

Therefore using the Mobius function, we get

$$\text{id} * \mu = (\varphi * 1) * \mu = \varphi * (1 * \mu) = \varphi * \varepsilon = \varphi.$$

In particular $$\varphi = \text{id} * \mu$$ is the Dirichlet convolution of two multiplicative functions and thus is multiplicative.

Moreover,

$$\varphi(n) = (\text{id} * \mu)(n) = (\mu * \text{id})(n) = \sum_{d\mid n} \mu(d)\text{id}(n/d) = n\sum_{d\mid n} \frac{\mu(d)}{d}.$$

:black_square_button:

**Corollary:** Let $$n=p_1^{k_1}p_2^{p_2}\dots p_r^{k_r}$$ for distinct primes $$p_1,\dots, p_r$$.  Then

$$\varphi(n) = (p_1^{k_1}-p_1^{k_1-1})(p_2^{k_2}-p_2^{k_2-1})\dots(p_r^{k_r}-p_r^{k_r-1}).$$

**Proof:**

This follows from multiplicativity and our expression for the value of $$\varphi$$ at the power of a prime.
:black_square_button:

**Example:**

We calculate $$\varphi(20) = \varphi(2^2\cdot 5) = \varphi(2^2)\varphi(5) = (2^2-2)(5-1) = 8.$$


