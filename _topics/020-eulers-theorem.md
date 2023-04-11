---
layout: page
title: Euler's Theorem
---

The principal application of Euler's totent function is that it provides a natural extension of Fermat's Little Theorem to residues of composite integers.

**Euler's Theorem:** Let $$n > 1$$ be a positive integer and suppose that $$a$$ is an integer with $$\gcd(a,n) = 1$$.  Then

$$a^{\phi(n)} = 1\mod n.$$

**Proof:**

Let $$r=\phi(n)$$ and let $$a_1,a_2,\dots, a_r$$ be the positive integers less than $$n$$ which are relatively prime to $$n$$.
Since $$a$$ is also relatively prime to $$n$$, the product $$aa_j$$ will be relatively prime to $$n$$ and therefore equivalent to a unique integer between $$1$$ and $$n-1$$ that is relatively prime to $$n$$.

Hence there is a function $$\sigma: \{1,2,\dots, r\}\rightarrow \{1,2,\dots, r\}$$ satisfying

$$aa_j\equiv a_{\sigma(j)}\mod n.$$

Moreover, since $$a$$ and $$n$$ are relatively prime, there exists a solution $$x=b$$ of the linear congruence equation

$$ax\equiv 1\mod n.$$

Naturally, the value $$b$$ is also relatively prime to $$n$$ and

$$ba_{\sigma(j)} = a_j.$$

It follows that $$\sigma$$ is a bijection.  Hence

$$\begin{align}
a_1a_2a_3\dots a_r
  & = a_{\sigma(1)}a_{\sigma(2)}a_{\sigma(3)}\dots a_{\sigma(r)}\\
  & \equiv (aa_1)(aa_2)(aa_3)\dots (aa_r) = a^ra_1a_2a_3\dots a_r.
\end{align}$$

In other words $$y=a_1a_2\dots a_r$$ satisfies

$$y \equiv a^ry\mod n.$$

Since $$y$$ is relatively prime to $$n$$, it follows that

$$1\equiv a^r\mod n$$.


:black_square_button:


**Example:**

We can tackle an old homework problem now very easily using Euler's theorem, namely the remainder of $$4444^{4444}$$ after dividing by $$9$$.
We have that

$$\phi(9) = \phi(3^2) = 3^2 - 3^1 = 6.$$

Therefore by Euler's theorem $$a^6\equiv 1\mod 9$$ for all $$a$$ relatively prime to $$9$$.

Since $$4440$$ is divisible by $$6$$, it follows that

$$4444^{4444} = 4444^4\cdot 4444^{4444}\equiv 4444^4\mod 9.$$

Moreover, $$4446$$ is divisible by $$9$$ and therefore $$4444\equiv -2\mod 9$$.

Hence

$$4444^{4444}\equiv (-2)^4 = 16\equiv 7\mod 9.$$

Thus the remainder is $$7$$.


**Example Problem:**

What are the last two digits of $$(12379)^{481}$$ ? 

