---
layout: page
title: Homework 3 Solution
permalink: /homework/hw3-soln
---

### Directions
Solve the following problems and type up your solutions.  Your solutions should be provided in one of the following formats (in order of preference)
* typed up in $$\LaTeX$$ and submitted as a PDF on Canvas
* written legibly on blank paper, scanned into a PDF and then uploaded on Canvas
* read aloud in class as a classic poem in iambic pentameter

If you go with the first strategy, you may wish to check out Overleaf which is a free and intuitive website for generating $$\LaTeX$$ documents online.
If you wish to use the second method and don't own a scanner at home, you can check out the numerous scanning apps available for smartphones.

**Problem 1:**

* (A) Prove that if $$n>1$$ is a composite integer, then it must have a prime divisor $$p$$ with $$1 <  p\leq\sqrt{n}$$.
* (B) Determine whether $$701$$ is prime by testing its divisibility by all primes $$\leq \sqrt{701} \approx 26.476$$
* (C) Determine whether $$1009$$ is prime by testing its divisibility by all primes $$\leq \sqrt{1009} \approx 31.76$$

**Solution:**

* (A) Since $$n$$ is composite, we can write $$n=ab$$ with $$1 < a \leq b$$.  Clearly $$a^2\leq ab=n$$ and therefore $$a\leq \sqrt{n}$$.  Thus any prime divisor of $$a$$ will be a prime divisor of $$n$$ which is $$\leq\sqrt{n}$$.
* (B) Just need to check the primes $$2,3,5,7,11,13,17,19,23$$
* (C) Just need to check the primes $$2,3,5,7,11,13,17,19,23,29,31$$

**Problem 2:**

Show that if $$n$$ is the product of three or more primes, then $$n$$ must be divisible by a prime $$p$$ with $$1\leq p\leq \sqrt[3]{n}$$.

**Solution:**

This is really just a generalization of what we worked out in (A) above.  We can write $$n=abc$$ for integers $$1 < a\leq b \leq c$$.
Then $$a^3\leq abc=n$$ and so $$a\leq \sqrt[3]{n}$$.  Thus any prime $$p$$ dividing $$a$$ will fit the bill.


**Problem 3:**

* (A) Prove that if $$2^n-1$$ is a prime number, then $$n$$ itself must also be a prime number.
* (B) Give an example of a prime integer which is not of the form $$2^p-1$$ for some prime $$p$$.
* (C) Show that $$2^{11}-1$$ is divisible by $$23$$ and therefore not prime.

**Solution:**

* (A) Suppose that $$n$$ is composite.  Then $$n=ab$$ with $$1 < a\leq b$$.  Therefore we can write

$$2^n-1 = 2^{ab}-1 = (2^a)^b-1 = (2^a-1)(1 + 2^a + 2^{2a} + \dots + 2^{(b-1)a}).$$

It follows that $$2^a-1$$ divides $$2^n-1$$.

* (B) $$5$$

* (C) We see that $$2^{11}-1 = 2047 = 23\cdot 89$$

**Problem 4:** 

A farmer purchased 100 head of livestock for a total cost of $4000. Prices were as follow:
calves, $120 each; lambs, $50 each; piglets, $25 each. If the farmer obtained at least one
animal of each type, how many of each did he buy?

**Solution:**

Let the number of calves, lambs, and piglets be $$c,l$$ and $$p$$, respectively.
We see that

$$\begin{align}
120c+50l+25p &= 4000\\
c + l + p %= 100
\end{align}$$

Putting these together $$95c+25l = 1500$$, or 

$$19c+5l = 300.$$

This is a linear Diophantine equation.
The numbers $$19$$ and $$5$$ are relatively prime, and in fact $$4\cdot 5 - 19 = 1$$.

Therefore the general solution is

$$\begin{align}
c &= -300 + 5k\\
l &= 1200 - 19k\\
p &= -800 +14k
\end{align}$$

Since we must have at least one type of animal, $$61\leq k \leq 63$$.  This gives three possible solutions:

* $$(c,l,p) = (5,41,54)$$
* $$(c,l,p) = (10,22,68)$$
* $$(c,l,p) = (15,3,82)$$

**Problem 5:** 

Use congruence to prove each of the following statements

* (A) $$13\mid 3^{n+2} + 4^{2n+1}$$
* (B) $$27\mid 2^{5n+1} + 5^{n+2}$$
* (C) $$43\mid 6^{n+2} + 7^{2n+1}$$

**Solution:**

* (A) $$3^{n+2} +  4^{2n+1} = 9\cdot 3^n + 4\cdot 16^n\equiv 9\cdot 3^n + 4\cdot 3^n = 13\cdot 3^n\equiv 0.$$
* (B) $$2^{5n+1}+5^{n+2} = 2\cdot 32^n+25\cdot 5^n\equiv 2\cdot 5^n+25\cdot 5^n=27\cdot 5^n\equiv 0.$$
* (C) $$6^{n+2} + 7^{2n+1} = 36\cdot 6^n + 7\cdot 49^n\equiv 36\cdot 6^n + 7\cdot 6^n = 43\cdot 6^n\equiv 0.$$

**Problem 6:**

Use congruence to prove

$$89\mid 2^{44}-1\quad\text{and}\quad 97\mid 2^{48}-1.$$

**Solution:**

We can write

$$2^{44}-1 = (2^11-1)(1+2^{11}+2^{22}+2^{33})$$

Furthermore

$$2^{11}-1 = 2047 = 23\cdot 89.$$

Therefore $$2^{44}-1$$ is divisible by $$89$$.


We can also write

$$2^{48}-1 = (2^{24}-1)(2^{24}+1)$$

Furthermore,

$$2^{24}+1 = (4096)^2+1\equiv 22^2+1\mod 97 \equiv 484+1 \equiv 0\mod 97.$$

Therefore $$2^{48}-1$$ is divisible by $$97$$.

**Problem: 7**

Let $$m>1$$ be an integer and $$p$$ be prime.  Choose $$k\geq 0$$ such that $$p^k \leq m < p^{k+1}$$.
Prove that the number of times $$p$$ divides $$m!$$ is

$$\sum_{j=1}^k \lfloor m/p^j \rfloor.$$


**Solution:**

For any integer $$x>0$$, let $$\nu_p(x)$$ be the number of times $$p$$ divides $$x$$.
Clearly $$\nu_p(ab) = \nu_p(a) + \nu_p(b)$$ and therefore 

$$\nu_p(m!) = \sum_{x=1}^m \nu_p(x).$$

Now $$\nu_p(x)=j$$ if and only if $$p^j\mid x$$ and $$p^{j+1}\nmid x$$.
Moreover

$$\lvert \{x: 1\leq x \leq m,\ p^j\mid x\}\rvert = \lfloor m/p^j\rfloor.$$

Thus we can write 

$$\begin{align}
\sum_{x=1}^m \nu_p(x)
 & = \sum_{j=1}^k j\lvert \{x: 1\leq x \leq m,\ \nu_p(x)=j\} \rvert\\
 & = \sum_{j=1}^k j\lvert \{x: 1\leq x \leq m,\ p^j\mid x,\ p^{j+1}\nmid x\} \rvert\\
 & = \sum_{j=1}^k j(\lvert \{x: 1\leq x \leq m,\ p^j\mid x\}\rvert - \lvert\{x: 1\leq x \leq m,\ p^{j+1}\nmid x\} \rvert)\\
 & = \sum_{j=1}^k j(\lfloor m/p^j \rfloor - \lfoor m/p^{j+1}\rfloor)\\
 & = \sum_{j=1}^k \lfloor m/p^j \rfloor
\end{align}$$

