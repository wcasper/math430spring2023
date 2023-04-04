---
layout: page
title: Dirichlet inverses
---

Given two multiplicative functions $$f(n)$$ and $$g(n)$$, we have already seen that Dirichlet convolution allows for the production of a third multiplicative function

$$(f* g)(n) = \sum_{d\mid n} f(d)g\left(\frac{n}{d}\right).$$

Thus Dirichlet convolution gives us an interesting way to *multiply* multiplicative functions.
This multiplication has a great many nice properties.

**Thorem:** Dirichlet convolution satisfies the following properties.

* (associativity) $$f* (g* h) = (f* g)* h$$
* (commutativity) $$f* g = g* f$$

This should remind us very much of an Abelian group, and indeed one could ask whether the multiplicative functions with Dirichlet convolution have *all* the properties of a group, such as an identity element and multiplicative inverses.
The answer, turns out to be *yes*.

For a multiplicative inverse, we have the following function

$$\varepsilon(n) = \left\lbrace\begin{array}{cc}1& n=1\\0& n\neq 1\end{array}\right.$$

:warning: **Careful!** One might be tempted to think that the identity function $$\text{id}$$ or the constant function $$1$$ is the multiplicative identity, but that is not true with respect to convolution!

**Theorem:**  Let $$f(n)$$ be any multiplicative function.  Then

$$(f* \varepsilon)(n) = (\varepsilon* f)(n) = f(n).$$

With this multiplicative identity established, we can consider the notion of inverses.

**Definition:** A **Dirichlet inverse** of a multiplicative function $$f(n)$$ is a multiplicative function $$g(n)$$ with the property that

$$(f* g)(n) = (g* f)(n) = \varepsilon(n).$$

It turns out that Dirichlet inverses are unique, and that almost all multiplicative functions have them.
In fact, one can work out directly what the multiplicative inverse $$g(n)$$ of $$f(n)$$ should be.

$$g(1)f(1) = \epsilon(1) = 1,\quad\text{so}\ g(1) = \frac{1}{f(1)}.$$

$$g(2)f(1) + g(1)f(2) = \epsilon(2) = 0,\quad\text{so}\ g(2) = - \frac{1}{f(1)}g(1)f(2)$$

$$g(3)f(1) + g(1)f(3) = \epsilon(3) = 0,\quad\text{so}\ g(3) = - \frac{1}{f(1)}g(1)f(3)$$

$$g(4)f(1) + g(2)f(2) + g(1)f(4) = \epsilon(4) = 0,\quad\text{so}\ g(4) = - \frac{1}{f(1)}(g(1)f(3)+g(2)f(2))$$

and so on.
Thus, we define an arithmetic function $$g(n)$$ recursively by $$g(1) = 1/f(1)$$ and

$$g(n) = -\frac{1}{f(1)}\sum_{d\mid n,\ d\neq n} g(d)f\left(\frac{n}{d}\right).$$

Of course, this only makes sense if $$f(1)\neq 0$$.
It is easy to check that $$g(n)$$ is again multiplicative, satisfies $$f* g= \varepsilon$$, and is the only function to satisfy this property.
To summarize, we have the following.

**Theorem:** Let $f(n)$ be a multiplicative function with $f(1)\neq 0$.  Then $f(n)$ has a unique Dirichlet inverse.

This means that the set of nonzero multiplicative functions forms an Abelian group.  Technically, it is a subgroup of the group of units of the **Dirichlet ring** of number-theoretic functions.

## The Mobius function

So far, we have a few particularly special multiplicative functions, namely
* the constant function $$1$$
* the number-of-divisors function $$\tau$$
* the sum-of-divisors function $$\sigma$$

These functions are already quite interesting!  Likewise, their Dirichlet inverses prove to be interesting objects to study, and are worth calculating explicitly.

For starters, let's try to get the Dirichlet inverse of the constant function $$f(1) = 1$$.
Since the inverse will be multiplicative, it suffices to obtain the value on powers of primes.
We have that $$g(1) = 1/f(1) = 1$$ and for $$k > 0$$

$$g(p^k)f(1) + g(p^{k-1})f(p) + \dots + g(p)f(p^{k-1}) + g(1)f(p) = \varepsilon(p^k) = 0.$$

Since $$f(n) = 1$$ always, this gives us $$g(p) = -1$$ and $$g(p^k) = 0$$ for $$k > 1$$.
Thus by multiplicativity

$$g(p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}) = g(p_1^{k_1})g(p_2^{k_2})\dots g(p_r^{k_r})$$

which will be zero if $$k_j>0$$ for any $$j$$ or else will be $$(-1)^r$$.
This leads to the definition of the Mobius function.

**Definition:** The **Mobius function** $$\mu(n)$$ is the arithmetic function defined by

$$\mu(n) = \left\lbrace\begin{array}{cc}
 1& \text{$n$ is square-free with an even number of prime factors}\\
-1& \text{$n$ is square-free with an odd  number of prime factors}\\
 0& \text{$n$ is divisible by the square of a prime
\end{array}\right.

Since the Mobius function is the Dirichlet inverse of $$1$$, we automatically obtain a very interesting formula, called the Mobius inversion formula.

**Theorem (Mobius Inversion Formula):**
Let $$f(n)$$ be a multiplicative function and

$$F(n) = \sum_{d\mid n} f(d).$$

Then 

$$f(n) = \sum_{d\mid n} f(d)\mu\left(\frac{n}{d}\right).$$

**Proof:**  We see that $$F = f * 1$$ and therefore

$$f = f * \epsilon = f * (1 * \mu)  = (1 * f)* \mu = F* \mu.$$

:black_square_button:

Since $$\tau = 1 * 1$$ and $$\sigma = \text{id} * 1$$, this provides us with some interesting equations for $$\tau$$ and $$\sigma$$.

**Corollary:**  The functions $$\tau$$ and $$\sigma$$ satisfy

$$\sum_{d\mid n} \tau(d)\mu\left(\frac{n}{d}\right) = 1,\quad\text{and}\quad \sum_{d\mid n} \sigma(d)\mu\left(\frac{n}{d}\right) = n.$$

**Proof:**  Just take $$f = 1$$ and $$f = \text{id}$$ in the previous theorem.

:black_square_button:

The Dirichlet inverses of $$\tau$$ and $$\sigma$$ can also be expressed in terms of the Mobius function.

**Theorem:** The Dirichlet inverses of $$\tau$$ and $$\sigma$$ are

$$\tau^{-1}(n) = (\mu * \mu)(n) = 2^{\omega(n)}$$

$$\sigma^{-1}(n) = (\mu * \text{id}\mu)(n) = \sum_{d\mid n} d\mu(d)\mu\left(\frac{n}{d}\right).$$

where here $$\omega(n)$$ denotes the number of *unique* prime divisors of $$n$$.


