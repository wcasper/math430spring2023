---
layout: page
title: Wilson's Theorem
---


**Wilson's Theorem:** Suppose that $$p$$ is prime.  Then $$p$$ divides $$(p-1)!+1$$.

**Proof:**

Let $$1\leq a < p$$.  Then $$a$$ and $$p$$ will be relatively prime, so the equation $$ax \equiv 1\mod p$$ will have a unique solution $$x=a'$$ with $$1\leq a' < p$$.
Now we divide the numbers $$1\leq a < p$$ into two disjoint sets:

$$A = \{a: 1\leq a < p,\ a^2\neq 1\},\ \text{and}\ B = \{b: 1\leq b < p,\ b^2= 1\}.$$

Then we can factor

$$(p-1)! = \left(\prod_{a\in A} a\right)\left(\prod_{b\in B} b\right).$$

Now for every $$a\in A$$ there exists a unique $$a'\in A$$ with $$aa' \equiv 1\mod p$$.  It follows that the product $$\prod_{a\in A}a \equiv 1\mod p$$.

On the other hand, if $$b\in B$$ then $$b^2-1\equiv 0\mod p$$ and therefore $$(b-1)(b+1)\equiv 0\mod p$$.  Since $$1\leq b < p$$, this means that either $$b=1$$ or $$b=p-1$$.
Thus $$B = \{1,p-1\}$$ and $$\prod_{b\in B}b = p-1\equiv -1\mod p$$.
We conclude that $$(p-1)!\equiv -1\mod p$$, proving our theorem.
:black_square_button:


The converse of Wilson's Theorem also turns out to be true: if $$(n-1)!+1$$ is divisible by $$n$$, then $$n$$ must be prime.
This gives an extremely concrete theoretical condition for the primality of $$n$$.
Unfortunately however, this is not of practical use for large values of $$n$$, since $$n!$$ becomes to enormous to deal with.

Let $$p$$ be a prime.
As an application of Wilson's Theorem, we can find solutions of the quadratic congruence equation

$$x^2 + 1\equiv 0\mod p.$$

As some initial observations, we see
* If $$p=2$$, then $$x=1$$ is a solution.
* If $$p=3$$, then no solutions exist.
* If $$p=5$$, then we get the solution $$x=2$$.

Let's explore this in more detail for arbitrary $$p$$.

By Fermat's Little Theorem, $$x^{p-1}\equiv 1\mod p$$.
For $$p>2$$, we know $$p$$ is odd, so we can write $$p-1=2j$$.
Thus if $$x^2+1\equiv 0\mod p$$ then
$$1 = \equiv x^{p-1} = x^{2j}\equiv (-1)^j\mod p.$$
In order for this to be true, $$j$$ must *also* be even ($j=2k$), meaning $$p=4k+1$$.
In other words, a solution cannot exist unless our prime is of the form $$p=4k+1$$.

Lastly, when $$p=4k+1$$ is a prime, we want to show that a solution of the quadratic congruence equation exists.
Our idea is to use Wilson's Theorem

$$1\cdot 2\cdot 3\cdot\dots\frac{p-1}{2}\cdot\frac{p+1}{2}\cdot\dots\cdot (p-1)\equiv -1\mod p.$$

We can rewrite this as

$$1\cdot (-1)\cdot 2\cdot (-2)\cdot\dots \cdot\frac{p-1}{2}\left(-\frac{p-1}{2}\right)\equiv -1\mod p.$$

This involves $$p-1/2 = 2k$$ copies of $$-1$$, an even number which cancel out.
Thus we see

$$1%2\cdot 2^2\cdot\dots \cdot\left(\frac{p-1}{2}\right)^2\equiv -1\mod p.$$

Hence we see that $$x = \left(\frac{p-1}{2}\right)!$$ is a solution of $$x^2+1\equiv 0\mod p$$.

To summarize, we have the following theorem.

**Theorem:** Let $$p$$ be a prime.  Then the quadratic congruence equation $$x^2+1\equiv 0\mod p$$ has a solution if and only if $$p=2$$ or $$p\equiv 1\mod 4$$.  In the latter case, a solution is given by $$x=((p-1)/2)!$$.


**Problem:** Find the remainder after $$2023!$$ is divided by $$2027$$.

**Solution:**
The number $$2027$$ is prime.
By Wilson's Theorem, we know that

$$2026!\equiv -1\mod 2027$$.

Therefore 

$$2026\cdot 2025\cdot 2024\cdot 2023!\equiv -1\mod 2027.$$

Equivalently

$$-1\cdot -2\cdot -3\cdot 2023!\equiv -1\mod 2027,$$

so that $$6\cdot 2023!\equiv 1\mod 2027.$$

Now $$2028$$ is divisible by both $$2$$ (even) and $$3$$ (sum of digits), and is therefore divisible by $$6$$.
Indeed $$2028=6\cdot 338$$, so $$338\cdot 6\equiv 1\mod 2027$$.
Consequently $$2023!\equiv 338\mod 2027$$.


