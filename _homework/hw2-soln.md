---
layout: page
title: Homework 2
permalink: /homework/hw2
---

### Directions
Solve the following problems and type up your solutions.  Your solutions should be provided in one of the following formats (in order of preference)
* typed up in $$\LaTeX$$ and submitted as a PDF on Canvas
* written legibly on blank paper, scanned into a PDF and then uploaded on Canvas
* read aloud in class as a classic poem in iambic pentameter

If you go with the first strategy, you may wish to check out Overleaf which is a free and intuitive website for generating $$\LaTeX$$ documents online.
If you wish to use the second method and don't own a scanner at home, you can check out the numerous scanning apps available for smartphones.

**Problem 1:**

Prove that for any integer $$n>1$$, the integer $$(10^n-1)/9$$ is not a perfect square.

**Solution:**

Interestingly, this is saying $$(10^n-1)/9 = 1111\dots1$$ is not a perfect square.

We will prove this by contradiction.
Suppose $$(10^n-1)/9  = k^2$$.  Then $$10^n-1 = 9k^2$$, and therefore $$k$$ must be odd, $$k=2j+1$$.
In particular

$$10^n-1=36j^2 + 36j + 9,$$

which says that

$$10(10^{n-1}-1) = 36 j(j+1).$$

The right hand side is divisible by $$4$$ but the left hand side is not, which is a contradiction.

**Problem 2:**

For any integer $$a>0$$, show that $$7a^3+5a$$ is divisible by $$6$$.

**Solution:**

We can write

$$7a^3+5a = 6(a^3+a) + a^3-a = 6(a^3+a) + (a-1)a(a+1).$$

By the Division Algorithm, any three sequential integers will include one divisible by $$3$$.
Likewise any two sequential integers will have one divisible by $$2$$.  Therefore $$(a-1)a(a+1)$$ is divisible by both $$2$$ and $$3$$.
Since these two numbers are relatively prime, it follows $$(a-1)a(a+1)$$ is divisible by $$6$$.
Hence $$7a^3+5a$$ is divisible by $$6$$.

**Problem 3:**

For each of the following statements, decide if the statement is true or false.
If it is true, prove it.  If it is false, provide a counter-example.

* (A) If $$a \mid b$$ then $$a \mid bc$$
* (B) If $$a \mid b$$ and $$a \mid c$$, then $$a^2 \mid bc$$
* (C) If $$a \mid b+c$$ then either $$a \mid b$$ or $$a \mid c$$


**Solution:**

* (A) True!  $$b = ka$$ implies $$bc = kca$$ which is divisible by $$a$$
* (B) True!  $$b = ja$$, $$c=ka$$, so $$bc=jka^2$$ is divisible by $$a^2$$
* (C) False!  $$5$$ divides $$10=3+7$$ but does not divide either $$3$$ or $$7$$

**Problem 4:** 

Let $$n\geq 1$$.  Prove each of the following statements.

* (A) $$8 \mid 5^{2n} + 7$$.
* (B) $$15 \mid 2^{4n} - 1$$
* (C) $$5 \mid 3^{3n+1}  + 2^{n+1}$$
* (D) $$21 \mid 4^{n+1} + 5^{2n-1}$$
* (E) $$24 \mid 2\cdot 7^n + 3\cdot 5^n - 5$$

**Solution:**

* (A)

$$5^{2n}+7 = 25^n+7 = (24+1)^n+7 = 8 + \sum_{k=1}^n\binom{n}{k}24^k.$$

* (B)

$$2^{4n}-1 = 16^n-1 = (15+1)^n-1 = \sum_{k=1}^n\binom{n}{k}15^k.$$

* (C)

$$3^{3n+1} + 2^{n+1} = 3\cdot 27^n + 2\cdot 2^n = 3\cdot(25+2)^n + 2\cdot 2^n = 5\cdot 2^n + \sum_{k=1}^n\binom{n}{k}25^k2^{n-k}.$$

* (D)

$$4^{n+1} + 5^{2n-1} = 4\cdot 4^n + 5\cdot 25^{n-1} = 16\cdot 4^{n-1} + 5\cdot (21+4)^{n-1} = 21\cdot 4^{n-1} + \sum_{k=1}^{n-1}\binom{n-1}{k}21^k4^{n-1-k}.$$

* (E)

We consider two cases: $$n =2k$$ and $$n=2k+1$$.

Suppose $$n=2k$$.  Then

$$2\cdot 49^k + 3\cdot 25^k - 5 = \sum_{j=1}^k \biniom{k}{j}(2\cdot 48^j+3\cdot 24^j).$$

Now suppose that $$n=2k+1$$.  Then

$14\cdot 49^k + 15\cdot 25^k - 5 = 25 + \sum_{j=1}^k \biniom{k}{j}(14\cdot 48^j+15\cdot 24^j).$$

**Problem 5:** 

Compute by hand the following

* (A) $$\gcd(143,227)$$
* (B) $$\gcd(306,657)$$
* (C) $$\gcd(272,1479)$$

**Solution:**

* (A) $$1$$
* (B) $$9$$
* (C) $$17$$

**Problem 6:**

Use the Euclidean algorithm to find integers $$x$$ and $$y$$ satisfying

* (A) $$\gcd(56,72) = 56x + 72y$$
* (B) $$\gcd(24,138) = 24x + 138y$$
* (C) $$\gcd(119,272) = 119x + 272y$$
* (D) $$\gcd(1769,2378) = 1769x + 2378y$$

**Solution:**

* (A) $$x=4$$, $$y=-3$$
* (B) $$x=6$$, $$y=-1$$
* (C) $$x=7$$, $$y=-3$$
* (D) $$x=39$$, $$y=-29$$

**Problem 7:**

Let $$a,b,n$$ be integers with $$n\geq 1$$.  Prove that if $$a^n \mid b^n$$ then $$a \mid b$$.

* Hint: use the following proposition, proved in class

**Proposition:** If $$a,b$$ and $$n$$ are positive integers, then $$\gcd(a^n,b^n) = \gcd(a,b)^n$$.

**Solution:**

Without loss of generality, $$a,b > 0$$.
We know that $$\gcd(a^n,b^n) = a^n$$, and therefore $$\gcd(a,b)^n = a^n$$.
Taking the $$n$$'th root of both sides, we get $$\gcd(a,b) = a$$ and therefore $$a\mid b$$.


