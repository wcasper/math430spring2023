---
layout: page
title: Euclidean Algorithm
---

In order to find the greatest common divisor of two integers, we can brute force things by listing the divisors of each integer and find the largest one the have in common.
This can be a pretty unhappliy long way to do things.
Luckily for us, Euclid gives us a nice strategy for finding the greatest common divisor, via repeated application of the Division Algorithm

## Euclidean Algorithm

Let $$a$$ and $$b$$ be two nonzero integers and without loss of generality, assume $$\lvert a/b\rvert > 1$$.
To get the greatest common divisor of $$a$$ and $$b$$, we use the following steps.

1. Use the Division Algorithm to obtain $$q_1$$ and $$r_1$$ with $$0\leq r_1 < \lvert b\rvert$$ and

$$a = qb + r_1.$$

2. Repeat the Division algorithm, but now with $$a$$ replaced by $$b$$ and $$b$$ replaced by $$r_1$$.  This gives integers $$q_2$$ and $$r_2$$ with $$0\leq r_2 < r_1$$ and

$$b = q_2r_1 + r_2.$$

3. Now recursively repeat the division algorithm to get $$r_{k+1}$$ and $$q_{k+1}$$ satisfying $$0\leq r_{k+1} < r_k$$ and

$$r_{k-1} = q_{k+1}r_k + r_{k+1}.$$

4. STOP when we get a remainder $$r_{n+1} = 0$$.

Since the sequence $$r_1,r_2,r_3$$ is a strictly decreasing sequence of integers bounded above by $$0$$, it must terminate eventually.

This leads to a **system of equations**:

$$\begin{align*}
a   &= q_1b + r_1\\
b   &= q_2r_1 + r_2\\
r_1 &= q_3r_2 + r_3\\
r_2 &= q_4r_3 + r_4\\
\dots \\
r_{n-3} &= q_{n-1}r_{n-2} + r_{n-1}
r_{n-2} &= q_{n}r_{n-1} + r_n
r_{n-1} &= q_{n+1}r_n + 0
\end{align*}$$

It is clear from the above system that $$r_n$$ divides $$r_k$$ for all $$k$$.  Consequently $$r_n$$ divides both $$a$$ and $$b$$.

Putting the equations together, we also find that

\begin{align*}
r_n
  & = r_{n-2} - q_nr_{n-1}\\
  & = r_{n-2} - q_n(r_{n-3}-q_{n-1}r_{n-2}) = (1-q_nq_{n-1})r_{n-2} - q_nr_{n-3}\\
  & \dots
\end{align*}

In this way, we will obtain an explicit expression of the form

$$r_n = ax + by$$

for some integers $$a$$ and $$b$$ defined in terms of thee quotients $$q_1,\dots, q_n$$.
This implies that $$r_n$$ is divisible by the greatest common divisor of $$a$$ and $$b$$.
Since $$r_n$$ divides both $$a$$ and $$b$$, we conclude that $$r_n$$ is *equal to* the greatest common divisor of $$a$$ and $$b$$.




