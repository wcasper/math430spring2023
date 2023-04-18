---
layout: page
title: Primitive roots modulo primes
---

While primitive roots do not exist in general, they will *always* exist modulo a prime number $$p$$.  In fact, a great numbeer of them exist, as is shown by the following theorem.

**Theorem:** Let $$p$$ be a prime number.  Then any integer relatively prime to $$\phi(p)=p-1$$ is a primitive root modulo $$p$$.  In particular there are $$\phi(p-1)$$ primitive roots modulo $$p$$, up to congruence modulo $$p$$.

We know already that the order of any element modulo $$p$$ must be a divisor of $$\phi(p)$$.  Thus a natural extension of the above result is to ask, given a divisor $$d$$ of $$\varphi(p)$$, how many elements are there whose order is $$d$$?

To answer this we need to establish a couple of results.

**Theorem:** Suppose that $$a$$ has order $$k$$ modulo $$n$$.  Then $$a^j$$ has order $$k/\gcd(k,j)$$ modulo $$n$$.

**Theorem:** Let $$f(x)$$ be a monic polynomial of degree $$n$$ with integer coefficients.  Then for any prime $$p$$, the equation

$$f(x) \equiv 0\mod p$$

has at most $$n$$ solutions up to equivalence modulo $$p$$.

**Corollary:** For any integer $$d$$ dividing $$p-1$$, the polynomial equation

$$x^d-1\equiv 0\mod p$$

has exactly $$d$$ solutions up to equivalence mod $$p$$.

As a consequence we have the following theorem which predicts the number of elments whose order is $$d$$ modulo $$p$$.

**Theorem:** Let $$p$$ be prime and let $$d\mid p-1$$.  Then there are exactly $$\phi(d)$$ many integers of order $$d$$ modulo $$p$$, up to equivalence mod $$p$$.



