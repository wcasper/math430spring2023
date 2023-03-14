---
layout: page
title: Fermat Factorization
---

The most basic way to try to factorize an integer $$n$$ is to check through all the numbers $$\leq\sqrt{n}$$ for a number which divides $$n$$.
The first real historical improvement over this method is to realize that finding a factorization of an odd integer is equivalent to writing an integer as the difference of squares.

In particular, if we can write $$n=x^2-y^2$$, then we can factor $$n=(x-y)(x+y)$$.
Conversely, suppose $$n = ab$$. 
Since $$n$$ is odd, both $$a$$ and $$b$$ are odd and therefore $$(a\pm b)/2$$ is an integer.
Then we can write

$$n = \left(\frac{a+b}{2}\right)^2-\left(\frac{a-b}{2}\right)^2.$$

as the difference of squares of two integers.
In this way, there is a bijective correspondence between the ways we can express $$n$$ as a difference of squares and the ways we can write $$n$$ as a product of two integers.

This motivates us to propose a method of factorizing integers, called Fermat's Factorization Method, where we try to express an integer $$n$$ as $$n=x^2-y^2$$.

**Fermat's Factorization Method:**
1. Find the smallest value of $$k>0$$ so that $$k^2-n\geq 0$$ (this is the first integer bigger than $$\sqrt{n}$$.
2. Increase $$k$$ by one until the expression $$k^2-n$$ is a perfect square.
3. If we find a perfect square for $$k < (n+1)/2$$, then $$x=k$$ and $$y=\sqrt(k^2-n)$$
4. If we get to $$k=\frac{n+1}{2}$$, then $k^2-n=\left(\frac{n-1}{2}\right)^2$$, giving us the factorization $$n=n\cdot 1$$.  In this case $$n$$ is prime.


**Example:**
Let's try to factor $$n=75261003596099$$.
We first find the smallest integer $$k>0$$ such that $$k^2-n$$
To do this, we calculate $$\sqrt{n}= 8675309.9999$$.
Therefore we should take $$k=8675310$$ to start out.
We calculate that for this value of $$k$$, $$k^2-n^2=1$$, which is a perfect square.
Hence we will have $$n^2=x^2-y^2$$ for $$x=8675310$$ and $$y=1$$.
This tells us we have a factorization $$n=(x-y)(x+y)$$, ie.
$$75261003596099 = 8675309\cdot 8675311.$$

**Example:**
Let's try to factor $$n=119$$.
We know that $$11^2 = 121$$, so we will start with $$k=11$$.
Unfortunately, $$k^2-n=2$$ is not a perfect square so we move to $$k=12$$.
We get that $$k^2-119=144-119=25$$ is a perfect square!
This tells us to take $$x=12$$ and $$y=5$$, giving us the factorization $$n=(x-y)(x+y)$$, ie. $$119=7\cdot17.$$

**Example:**
Let's try to factor $$n = 119143$$.

$$\begin{align}
346^2 - 119143 &= 119716 - 119143 = 573\\
347^2 - 119143 &= 120409 - 119143 = 1266\\
348^2 - 119143 &= 121104 - 119143 = 1961\\
349^2 - 119143 &= 121801 - 119143 = 2658\\
350^2 - 119143 &= 122500 - 119143 = 3357\\
351^2 - 119143 &= 123201 - 119143 = 4058\\
352^2  - 119143 &= 123904 - 119143 = 4761 = 69^2
\end{align}$$

Therefore we take $$x=352$$ and $$y=69$$, meaning

$$119143 = (352-69)(352+69) = 283\cdot 421.$$



