---
layout: page
title: Prime numbers
---


## What's the right definition of prime?
Prime numbers are the multiplicative building blocks of the integers.
The definition of a prime number that we are used to from elementary school is the following.

**Definition:** A positive number $$p$$ is called **prime** if its only positive divisors are $$1$$ and $$p$$.

The unfortunate part of this definition is that as far as *ring theory* is concerned, its close to the definition of an irreducible element.
Suppose that $$R$$ is a commutative ring, such as $$\mathbb{Z}$$ or $$\mathbb{R}$$ or $$\mathbb{Q}$$.

**Definition:** An element $$u\in R$$ is called a **unit** if it is invertible in $$R$$.  Then $$a$$ is called **irreducible** if the only divisors of $$a$$ are units or unit multiples of $$a$$.  An element $$p\in R$$ is called **prime** if and only if when $$p$$ divides $$ab$$, then either $$p$$ divides $$a$$ or $$p$$ divides $$b$$.

In *any* commutative ring $$R$$ without zero divisors, primes are necessarily irreducible.  However irreducibles may not be prime.

**Theorem:**  Primes are irreducible.

**Proof:** Suppose that $$p$$ is prime and that $$p = ab$$.  Then either $$p$$ divides $$a$$ or $$p$$ divides $$b$$.
Without loss of generality, let us suppose that $$p$$ divides $$a$$.  Then we can write $$a = pc$$ for some $$c\in R$$ and therefore $$p = bcp$$.
Hence $$1 = bc$$, making $$b$$ and $$c$$ units.  Thus the only divisors of $$p$$ are units and unit multiples of $$p$$.
:black_square_button:

Luckily for us, in the ring of integers things are much simpler.  In particular, irreducibles and primes are the same thing.

**Theorem:** An irreducible $$p\in\mathbb{Z}$$ is necessarily prime.

**Proof:** Suppose that $$a$$ is irreducible and that $$a \mid bc$$.  If $$a \mid b$$, great.  Otherwise, $$\gcd(a,b) = 1$$ and therefore we can find $$x$$ and $$y$$ with $$ax + by = 1$$.  Multiplying this by $$c$$, we get $$acx + bcy = c$$.  The left hand side is divisible by $$a$$, thus $$c$$ is divisible by $$a$$.
Hence in either case, $$a$$ divides $$b$$ or $$c$$ and $$a$$ is prime.
:black_square_button:

So in the end, who is right?
The answer is that for integers, the usual definition of a prime is *just fine*.  The more general definition of a prime becomes important when we want to consider other, interesting rings.

## Fundamental theorem of arithmetic

**Theorem:** Let $$n > 1$$.  Then $$n$$ can be written as a product of primes.  Moreover, the primes occuring in this product are unique up to reordering.

**Proof:**  

We proceed via strong induction.
If $$n=2$$, then $$n$$ is prime.
As an inductive assumption, suppos that for some $$m\geq 2$$, every number $$1 < k \leq m$$ can be written as a product of primes.
We must show that $$m+1$$ can be written as a product of primes.

If $$m+1$$ is prime, great.
Otherwise, the set $$S = \{d:\ d\mid(m+1),\ \ 1 < d < m+1\}$$ is a nonempty set of positive integers.
By the Well-Ordering Principle, this has a smallest element $$d$$.
By virtue of its minimality, $$d$$ is prime.
Furthermore, by the inductive assumption $$(m+1)/d$$ may be written as a $$(m+1)/d = p_1p_2\dots p_r$$.
Thus $$m+1 = dp_1p_2\dots p_r$$ is a product of primes.

To finish the proof, we must show that products of primes must be unique, up to reordering.
Suppose

$$p_1p_2\dots p_r = q_1q_2\dots q_s$$

for some primes $$p_1,\dots, p_r$$ and $$q_1,\dots, q_s$$.
Since $$p_r$$ is prime and $$p_1$$ divides $$q_1\dots q_r$$, $$p_r$$ must divide one of the elements $$q_j$$ for some $$j$$.
By reordering the elements on the right hand side, without loss of generality we can assume $$j=s.$$
Since $$q_s$$ is prime, it follows that $$p_r = q_s$$.
Now we have 

$$p_1p_2\dots p_{r-1} = q_1q_2\dots q_{s-1}.$$

If $$r < s$$, we end up with the expression

$$1 = q_1q_2\dots q_{s-r},$$

which is impossible.  Otherwise, we end up with $$p_1=q_1,p_2=q_2,\dots,p_r=q_r$$.

:black_square_button:

**Example:** $$136 = 2\cdot 2\cdot 2\cdot 17$$


Sometimes, we would like to write primes down in terms of repeating powers.  This is the so-called **canonical form**.

**Theorem:** Let $$n > 1$$ be an integer.  Then there exist *unique* primes $$p_1,\dots, p_r$$ and unique positive integers $$m_1,\dots, m_r$$ with

$$n = p_1^{m_1}p_2^{m_2}\dots p_r^{m_r}.$$

The number $$m_j$$ is called the **multiplicity** of the prime $$p_j$$.




