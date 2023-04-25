---
layout: page
title: Quadratic congruence
---

A **quadratic congruence** is an equation of the form

$$ax^2+bx + c\equiv 0\mod n.$$

Here, $$a, b, c$$ and $$n$$ are known and typically $$\gcd(a,n) = 1$$.
We are searching for the values of $$x$$ satisfying this equation, of which there will be at most finitely many modulo $$n$$.
Just like with linear congruence equations, solutions need not exist!

**Example:** There are no solutions of $$x^2+1\equiv 0\mod 4$$.

So under what conditions can we say that a solution exists?  Let's look at the specific case when $$n=p$$ is an odd prime and $$a$$ is not divisible by $$p$$.
In this case, we can multiply by a multiplicative inverse of $$a$$ to obtain

$$x^2+a^{-1}bx + a^{-1}c\equiv 0\mod p.$$

Now since $$p$$ is odd, we can complete the square to write

$$(x+2^{-1}a^{-1}b)^2 \equiv 2^{-2}a^{-2}(b^2-4ac)\mod p.$$

So we see that the original equation has a solution if and only if the expression $$b^2-4ac$$ may be expressed as a square modulo $$p$$.
This motivates the following definition.

**Definition:** An number $$a$$ is called a **quadratic residue modulo $$n$$** if and only if $$a$$ is equivalent to a perfect square modulo $$n$$.  If $$n$$ is not a quadratic residue modulo $$n$$, it is called a **quadratic nonresidue modulo $$n$$**.


**Example:**

Consider the quadratic congruence

$$6x^2 + 5x + 1 \equiv 0 \mod 17.$$

Note that $$5^2-4\cdot 6\cdot 1 = 1$$ is a perfect square, so the equation should have a solution.

Note that $$6\cdot 3 = 18$$ and so $$3$$ is a multiplicative inverse of $$6$$.
Using this, we reduce our equation to

$$x^2 + 15x + 3 \equiv 0 \mod 17.$$

Now $$2$$ has multiplicative inverse $$9$$ so we can factor this as

$$(x+9\cdot 15)^2 \equiv 9^2\cdot 15^2 - 3\mod 17.$$

We can rewrite this as

$$(x+9\cdot 15)^2 \equiv 9^23^2\cdot (5^2 - 4\cdot 6)\mod 17.$$

or rather

$$(x-1)^2 \equiv 9^23^2\mod 17.$$

Now since $$17$$ is prime, we see 

$$x-1 \equiv \pm 10\mod 17.$$

This gives us two solutions: $$x=11$$ and $$x=-9$$.  These are all solutions, up to equivalence modulo $$17$$.
:black_square_button:

To summarize, we have the following theorem.

**Theorem:**
Let $$p$$ be an odd prime and $$a,b,c$$ are integers with $$p\nmid a$$.
Then the quadratic residue equation

$$ax^2 + bx + c\equiv 0\mod p$$

has a solution if and only if $$b^2-4ac \equiv d^2\mod p$$ for some integer $$d$$.
In this case, if $$d$$ is not divisible by $$p$$, we have exactly two solutions, given by

$$x = 2^{-1}a^{-1}(-b-d)\quad\text{and}\quad x = 2^{-1}a^{-1}(-b+d)$$

where here $$2^{-1}$$ and $$a^{-1}$$ represent mulitplicative inverses modulo $$p$$.

If $$d$$ is divisible by $$p$$, then we have only the single solution $$x= -2^{-1}a^{-1}b$$.

**Proof:**
It follows from the discussion above that these are two solutions.  Since the polynomial equation can have at most two solutions, this must be all solutions whenever $$d$$ is not equivalent to $$0$$ modulo $$p$$.  When $$d$$ is equivalent to zero, we have repeated root of the original equation, again giving us a single solution.
:black_square_button:

As we see here, the crux of the matter is whether or not a particular number is a quadratic residue.
Luckily for us, Euler gives us a nice condition for a number being a quadratic residue.

**Theorem:** Let $$p$$ be an odd prime and $$a$$ is an integer with $$p\nmid a$$.  Then $$a$$ is a quadratic residue modulo $$p$$ if and only if $$a^{(p-1)/2}\equiv 1\mod p.$$

**Proof:** 

Suppose that $$a$$ is a quadratic residue modulo $$p$$.
Then $$a\equiv b^2\mod p$$ for some $$b$$ and since $$p$$ doesn't divide $$a$$, it won't divide $$b$$ either.  Thus by Fermat's Little Theorem, $$a^{(p-1)/2}\equiv b^{p-1}\equiv 1\mod p.$$

Conversely, suppose that $$a^{(p-1)/2}\equiv 1\mod p.$$
Choose a primitive root $$r$$ modulo $$p$$, ie. an element $$r$$ of order $$p-1$$.
Then $$a=r^{j}$$ for some $$j$$, from which we find the order of $$a$$ is $$(p-1)/\gcd(j,p-1)$$.
Consequently $$(p-1)/\gcd(j,p-1)$$ divides $$(p-1)/2$$, making $$(p-1)\gcd(j,p-1) = 2k(p-1)$$ for some integer $$k$$.
Hence $$\gcd(j,p-1)=2k$$, forcing $$r$$ to be even.  It follows that $$b=r^{j/2}$$ is an integer and $$a=b^2$$.
Hence $$a$$ is a quadratic residue.

:black_square_button:

Now if $$a^{(p-1)/2}\not\equiv 1\mod p$$, then what could it be?  It's square is $$1$$ modulo $$p$$, so it has to be either $$1$$ or $$-1$$, depending on whether $$a$$ is a quadratic residue or nonresidue.

**Corollary:**

Let $$p$$ be an odd prime and $$a$$ be an integer not divisible by $$p$$.
Then

$$a^{(p-1)/2}\equiv \left\lbrace \begin{array}{cc} 1 & \text{$a$ is a quadratic residue}\\ -1 & \text{$a$ is a quadratic nonresidue}\end{array}\right.$$

This is motivates the definition of the Legendre symbol, given below.

**Definition**  Let $$p$$ be an odd prime.  The **Legendre symbol** $$(a/p)$$ is defined by

$$(a/p) =  \left\lbrace \begin{array}{cc} 1 & \text{$a$ is a quadratic residue}\\ -1 & \text{$a$ is a quadratic nonresidue}\end{array}\right.$$





