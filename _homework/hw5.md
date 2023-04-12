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

Prove that Dirichlet convolution is commutative, ie if $$f(x)$$ and $$g(x)$$ are two arithmetic functions, then

$$(f * g)(n) = (g * f)(n)$$

for all natural numbers $$n$$.

**Problem 2:**

Prove the following

* (a) $$\tau(n)$$ is an odd integer if and only if $$n$$ is a perfect square
* (b) $$\sigma(n)$$ is an odd integer if and only if $$n$$ is a perfect square or twice a perfect square

**Problem 3:**

For any integer $$s\geq 0$$, consider the arithmetic function

$$\sigma_s(n) = \sum_{d\mid n} d^s.$$

* (a) Explain why $$\sigma_0 = \tau$$ and $$\sigma_1 = \sigma$$
* (b) Show that $$\sigma_s$$ is multiplicative
* (c) Let $$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$ for distinct prime divisors $$p_1,\dots p_r$$.  Prove

$$\sigma_s(n) = \left(\frac{p_1^{s(k_1+1)}-1}{p_1^s-1}\right)\left(\frac{p_2^{s(k_2+1)}-1}{p_2^s-1}\right)\dots\left(\frac{p_r^{s(k_r+1)}-1}{p_r^s-1}\right).$$


**Problem 4:** 

Let $$n = p_1^{k_1}p_2^{k_2}\dots p_r^{k_r}$$ for distinct prime divisors $$p_1,\dots p_r$$.  Prove the following

[Hint: prove (a) and then use (a) to prove all the other expressions.]

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


**Problem 5:** Use Euler's Theorem to evaluate

$$2^{100000}\mod 77.$$



