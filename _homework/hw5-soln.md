---
layout: page
title: Homework 5
permalink: /homework/hw5
---

### Directions
Solve the following problems and type up your solutions.  Your solutions should be provided in one of the following formats (in order of preference)
* typed up in $$\LaTeX$$ and submitted as a PDF on Canvas
* written legibly on blank paper, scanned into a PDF and then uploaded on Canvas
* submitted as an issue to the Twitter algorithm public source code on Github [thanks Elon :( ]

If you go with the first strategy, you may wish to check out Overleaf which is a free and intuitive website for generating $$\LaTeX$$ documents online.
If you wish to use the second method and don't own a scanner at home, you can check out the numerous scanning apps available for smartphones.

**Problem 1:**

Prove that Dirichlet convolution is commutative, ie if $$f(x)$$ and $$g(x)$ are two arithmetic functions, then

$$(f * g)(n) = (g * f)(n)$$

for all natural numbers $$n$$.

**Proof:**

Let $$d_1,d_2,d_3,\dots, d_r$$ be the divisors of $$n$$ in increasing order.

Then $$n/d_i = d_{r-i+1}$$ and

$$(f * g)(n) = \sum_{d\mid n} f(d)g(n/d) = f(d_1)g(d_r) + f(d_2)g(d_{r-1}) + \dots + f(d_{r-1})g(d_2) + f(d_r)g(d_1).$$

Likewise 

$$(g * f)(n) = \sum_{d\mid n} g(d)f(n/d) = f(d_r)g(d_1) + f(d_{r-1})g(d_2) + \dots + f(d_2)g(d_{r-1}) + f(d_1)g(d_r).$$

Thus the second sum is just the same as the first sum, only the order that we add the values is reversed.
:black_square_button:

**Problem 2:**

Prove the following

* (a) $$\tau(n)$$ is an odd integer if and only if $$n$$ is a perfect square
* (b) $$\sigma(n)$$ is an odd integer if and only if $$n$$ is a perfect square or twice a perfect square

**Proof:**

* (A) Let suppose that $$n$$ has the prime factorization $$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$ for some distinct primes $$p_1,\dots, p_r$$ and some positive integers $$k_1,\dots,k_r$$.
Then 

$$\tau(n) = (k_1+1)(k_2+1)\dots (k_r+1)$$

If $$\tau(n)$$ is odd, then $$k_j+1$$ must be odd for all $$j$$ and threfore $$k_j$$ must be even for all $$j$$.  It follows that
$$n = (p_1^{k_1/2}p_2^{k_2/2}\dots p_r^{k_r/2})^2$$
is the square of an integer and thus a perfect square.

Conversely, if $$n=m^2$$ for some integer $$m$$, then we can consider the prime factorization $$m=q_1^{\ell_1}q_2^{\ell_2}\dots q_s^{\ell_s}$$.  It follows that $$n = m^2 = q_1^{2\ell_1}q_2^{2\ell_2}\dots q_s^{2\ell_s}$$ and since prime factorizations are unique up to reordering, we can conclude that $$r=s$$, $$p_j=q_j$$ and $$k_j=2\ell_j$$ for all $$j$$.  Consequently $$k_j$$ is even for all $$j$$ making $$\tau(n)$$ odd.

* (B) Let suppose that $$n$$ has the prime factorization $$n = 2^tp_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$ for some distinct odd primes $$p_1,\dots, p_r$$, some positive integers $$k_1,\dots,k_r$$, and some integer $$t\geq 0$$ (so $$t=0$$ when $$n$$ is odd).
Then

$$\sigma(n) = \sigma(2^t)\sigma(p_1^{k_1})\sigma(p_2^{k_2})\dots\sigma(p_r^{k_r}).$$

Note that $$\sigma(2^t) = 1 + 2 + \dots + 2^t$$, which is always odd.
Moreover, $$\sigma(p_j^{k_j}) = 1 + p_j + \dots + p_j^{k_j}$$ is a sum of $$k_j+1$$ many odd numbers and is odd if and only if $$k_j$$ is even.
Therefore $$\sigma(n)$$ is odd if and only if $$k_j$$ is even for all $$j$$, *regardless* of the value of $$t$$.

We consider two separate cases: when $$t$$ is even and when $$t$$ is odd.

- If $$t$$ is even and $$\sigma(n)$$ is odd, then $$n=(2^{t/2}p_1^{k_1/2}p_2^{k_2/2}\dots p_r^{k_r/2})^2$$ is the square of an integer and thus a perfect square.
- If $$t$$ is odd and $$\sigma(n)$$ is odd, then $$n=2(2^{(t-1)/2}p_1^{k_1/2}p_2^{k_2/2}\dots p_r^{k_r/2})^2$$ is two times a perfect square.

Conversely, if $$n$$ is either a perfect square or twice a perfect square, then the same argument as in (A) using the uniqueness of the prime factorization implies that $$k_j$$ is even for all $$j$$ and thus that $$\sigma(n)$$ is odd.
:black_square_button:

**Problem 3:**

For any integer $$s\geq 0$$, consider the arithmetic function

$$\sigma_s(n) = \sum_{d\mid n} d^s.$$

* (a) Explain why $$\sigma_0 = \tau$$ and $$\sigma_1 = \sigma$$
* (b) Show that $$\sigma_s$$ is multiplicative
* (c) Let $$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$ for distinct prime divisors $$p_1,\dots p_r$$.  Prove

$$\sigma_s(n) = \left(\frac{p_1^{s(k_1+1)}-1}{p_1^s-1}\right)\left(\frac{p_2^{s(k_2+1)}-1}{p_2^s-1}\right)\dots\left(\frac{p_r^{s(k_r+1)}-1}{p_r^s-1}\right).$$

**Solution:**

* (A) Clearly $$\sigma_0(n) = \sum_{d\mid n}d^0 = \sum_{d\mid n} 1$$ counts the number of divisors, and is thus $$1$$.  Likewise $$\sigma_1 = \sigma$$.
* (B) The function $$f_s(n)=n^s$$ is multiplicative for all integers $$s\geq 0$$ and $$\sigma_s$$ is the Dirichlet convolution $$\sigma_s = f_s * f_0$$, hence it is multiplicative.
* (C) Recall the geometric sum $$\sum_{j=0}^k a^j = \frac{a^{k+1}-1}{a-1}$$.  Thus for any prime $$p$$,

$$\sigma_s(p^k) = \sum_{d\mid p^k} d^s = \sum_{j=0}^k (p^s)^j = \frac{p^{s(k+1)}-1}{p^s-1}.$$

Since $$\sigma_s$$ is multiplicative, it follows that

$$\sigma_s(n) = \sigma_s(p_1^{k_1})\sigma_s(p_2^{k_2})\dots\sigma_s(p_r^{k_r}) = \left(\frac{p_1^{s(k_1+1)}-1}{p_1^s-1}\right)\left(\frac{p_2^{s(k_2+1)}-1}{p_2^s-1}\right)\dots\left(\frac{p_r^{s(k_r+1)}-1}{p_r^s-1}\right).$$
:black_square_button:

**Problem 4:** 

Let $$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$ for distinct prime divisors $$p_1,\dots p_r$$.  Prove the following

* (a) For any multiplicative function $$f(n)$$

$$\sum_{d\mid n} \mu(d)f(d) = (1-f(p_1))(1-f(p_2))\dots(1-f(p_r))$$

* (b)

$$\sum_{d\mid n} \mu(d)\tau(d) = (-1)^r$$

* (c)

$$\sum_{d\mid n} \mu(d)\sigma(d) = (-1)^rp_1p_2\dots p_r$$

* (d)

$$\sum_{d\mid n} \mu(d)d = (1-p_1)(1-p_2)\dots (1-p_r)$$

* (e)

$$\phi(n) = n\prod_{j=1}^r \left(1-\frac{1}{p_j}\right).$$

* (f)

$$\sum_{d\mid n} \mu(d)\phi(d) = (2-p_1)(2-p_2)\dots (2-p_r)$$


**Proof:**

* (A) Using the explicit value of $$\mu$$ and the fact that $$f$$ is multiplicative, we calculate

$$\begin{align}
\sum_{d\mid n} \mu(d)f(d)
 & = \sum_{j_1=0}^{k_1}\sum_{j_2=0}^{k_2}\dots \sum_{j_r=0}^{k_r} \mu(p_1^{j_1}p_2^{j_2}\dots p_r^{j_r})f(p_1^{j_1}p_2^{j_2}\dots p_r^{j_r})\\
 & = \sum_{j_1=0}^{1}\sum_{j_2=0}^{1}\dots \sum_{j_r=0}^{1} \mu(p_1^{j_1}p_2^{j_2}\dots p_r^{j_r})f(p_1^{j_1}p_2^{j_2}\dots p_r^{j_r})\\
 & = \sum_{j_1=0}^{1}\sum_{j_2=0}^{1}\dots \sum_{j_r=0}^{1} (-1)^{j_1+j_2+\dots + j_r}f(p_1^{j_1})f(p_2^{j_2})\dots f(p_r^{j_r})\\
 & = \left(\sum_{j_1=0}^{1}(-1)^{j_1}f(p_1^{j_1})\right)\left(\sum_{j_2=0}^{1}(-1)^{j_2}f(p_2^{j_2})\right)\dots \left(\sum_{j_r=0}^{1}(-1)^{j_r}f(p_r^{j_r})\right)\\
 & = (1-f(p_1))(1-f(p_2))\dots (1-f(p_r)).
\end{align}$$

* (B) Now using (A), 

$$\sum_{d\mid n} \mu(d)\tau(d) = (1-\tau(p_1))(1-\tau(p_2))\dots(1-\tau(p_r)) = (1-2)(1-2)\dots(1-2)= (-1)^r.$$

* (C) Again using (A)

$$\sum_{d\mid n} \mu(d)\sigma(d) = (1-\sigma(p_1))(1-\sigma(p_2))\dots (1-\sigma(p_r)) = (1-(1+p_1))(1-(1+p_2))\dots(1-(1+p_r)) = (-1)^rp_1p_2\dots p_r.$$

* (D) Using (A) once more with $$f(n) = n$$ the identity function, the result follows immediately.

* (E) Using (A) with $$f(n) = 1/n$$, combined with the Mobius inversion formula for the totent function we have that

$$\phi(n) = n\sum_{d\mid n}\mu(d)\frac{1}{d} = n(1-1/p_1)(1-1/p_2)\dots(1-1/p_r).$$

* (F) This again just follows from (A) with $$f=\phi$$.


**Problem 5:** Use Euler's Theorem to evaluate

$$2^{100000}\mod 77.$$

**Solution:** 

We first calculate $$\phi(77) = \phi(11\cdot 7) = \phi(11)phi(7) = 10\cdot  6 = 60.$$

Therefore Euler's Theorem tells us $$2^{60}=1\mod 77$$.  Thus we can write

$$2^{100000} = 2^{99960+40} = (2^{60})^{16666}2^{40}\equiv 2^{40}\mod 77.$$

Now we want to know what $$x = 2^{40}$$ actually is.  By Fermat's Little Theorem, $$2^{40}\equiv 1\mod 11$$.  Moreover, $$2^3=1\mod 7$$ so $$2^{40}\equiv 2\mod 7$$.
Thus $$x$$ satisfies the system of linear congruence equations

$$\begin{align}
x\equiv 2\mod 7\\
x\equiv 1\mod 11
\end{align}$$

We propose a solution of the form $$x = 11a + 7b$$.  Then $$11a\equiv 2\mod 7$$ so that $$a=4$$.  Likewise $$7b\equiv 1\mod 11$$ so that $$b=-3$$.
This gives us the solution $$x=11\cdot 4- 7\cdot 3 = 23$$.

We conclude that $$2^{100000}$$ is equivalent to $$23$$ modulo $$77$$.

