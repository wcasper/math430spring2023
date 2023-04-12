---
layout: page
title: Homework 4 Solutions
permalink: /homework/hw4-soln
---

### Directions
Solve the following problems and type up your solutions.  Your solutions should be provided in one of the following formats (in order of preference)
* typed up in $$\LaTeX$$ and submitted as a PDF on Canvas
* written legibly on blank paper, scanned into a PDF and then uploaded on Canvas
* encoded into a modern interpretive dance routine, set to the tune of Yanky Doodle

If you go with the first strategy, you may wish to check out Overleaf which is a free and intuitive website for generating $$\LaTeX$$ documents online.
If you wish to use the second method and don't own a scanner at home, you can check out the numerous scanning apps available for smartphones.

**Problem 1:**

Prove that a number is divisible by $$3$$ if and only if the sum of its digits (base $$10$$) is divisible by $$3$$.

**Proof:**

Suppose that $$n$$ has digits

$$n=d_rd_{r-1}d_{r-2}\dots d_1d_0.$$

Then

$$n = d_0 + 10d_1 + 100d_2 + \dots + 10^rd_r.$$

Since $$10\equiv 1\mod 3$$, it follows that

$$n\equiv d_0 + d_1 + \dots + d_r\mod 3.$$

Now $$n$$ is divisible by $$3$$ if and only if $$n\equiv 0$$ mod $$3$$,
it follows that $$n$$ is divisible by $$3$$ if and only if the sum of its digits is equivalent to zero modulo $$3$$, which is true if and only if the sum of the digits is divisible by $$3$$.
:black_square_button:

**Problem 2:**

Determine the last two digits of $$9^{9^9}$$.  [Hint: first consider the value of the exponent $$9^9$$ modulo $$10$$.]

**Solution:**

Since $$9\equiv -1\mod 10$$ we have $$9^9 \equiv (-1)^9 = -1 \mod 10$$.
In particular, we can write $$9^9 = -1 + 10k$$ for some integer $$k$$.

$$9^{9^9} = 9^{-1 + 10k} = (10-1)^{-1+10k} = -1 + \binom{10k-1}{1}10 - \binom{10k-1}{2}100 + \dots - \binom{10k-1}{10k-1}10^{10k-1}.$$

Therefore modulo $$100$$

$$9^{9^9}\equiv -1 + \binom{10k-1}{1}10 = -1 -10+100k\equiv -1 - 10\equiv 89.$$

Thus the last two digits are $$89$$.

**Problem 3:**

Find the remainder when $$4444^{4444}$$ is divided by $$9$$.

**Solution:**

Since $$9$$ divides $$4446$$, we can write

$$4444^{4444} = (4446-2)^{4444}\equiv (-2)^{4444} = 2^{4444}.$$

Then since $$3$$ divides $$4443$$, and $$8\equiv -1\mod 9$$, we see

$$4444^{4444}\equiv 2\cdot 2^{4443} = 2\cdot 8^{1481} \equiv 2\cdot (-1)^{1481} \equiv -2\equiv 7\mod 9.$$

Thus the remainder is $$7$$.

**Problem 4:** 

Convert each of the following numbers to the specified base.

* (A) $$127$$ to base $$2$$
* (B) $$1010101_2$$ to base $$10$$
* (C) $$233$$ to base $$6$$.

**Solution:**

* (A) Since $$128 = 2^7$$, we know that

$$127 = 2^7-1= 2^6 + 2^5 + 2^4 + 2^3 + 2^2 + 2^1 + 2^0$$

and therefore the binary expansion of $$127$$ is $$1111111_2$$.

* (B) We calculate

$$1010101_2 = 2^6 + 2^4 + 2^2 + 2^0 = 4^0 + 4^1 + 4^2 + 4^3 = \frac{4^4-1}{4-1} = 255/3 = 85$$


* (C) We get $$6^3 = 216$$, and $$233-216=17 = 2\cdot 6 + 5$$.

This means that

$$216 = 6^3 + 2\cdot 6^1 + 5\cdot 6^0$$

and therefore the base 6 expansion of $$233$$ is $$6025_6$$.

**Problem 5:** 

Solve the following linear congruences.

* (A) $$36x\equiv 8\mod 102$$
* (B) $$34x\equiv 60\mod 98$$
* (C) $$140x\equiv 133\mod 301$$

**Solution:**

* (A) Since $$\gcd(36,102)=6$$, and $$6\nmid 8$$ the linear congruence has no solution.

* (B) Since $$\gcd(34,98) = 2$$ and $$2\mid 60$$ the linear congruence has a solution.  Moreover, we can work with the reduced form $$17x\equiv 30\mod 49.$$
Now $$17\cdot 3 = 51=2\mod 49$$, and $$2\cdot 25 = 50\equiv 1\mod 49$$ so that $$17\cdot 75\equiv 1\mod 49$$.
In other words, $$75\equiv 26$$ is a multiplicative inverse of $$17$$.  Multiplying both sides of our linear congruence by $$26$$, we get

$$x\equiv 26\cdot 17x \equiv 26\cdot 30 = 780\equiv 45.$$

Thus all solutions of the original linear congruence are of the form $$45 + 49k$$ for some integer $$k$$.

* (C) Since $$\gcd(140,301) = 7$$ and $$7\mid 133$$, the linear congruence has a solution.  Moreover, we can work with the reduced equation $$20x\equiv 19\mod 43$$.
Now since $$20\cdot 2 = 40\equiv -3$$ and $$-3\cdot 14 = -42\equiv 1$$, we get that $$2\cdot 14 = 28$$ is a multiplicative inverse of $$20$$ modulo $$43$$.
It follows that

$$x\equiv 28\cdot 20x\equiv 28\cdot 19 = 541\equiv 25\modulo 43$$.

Thus all solutions of the original linear congruence are of the form $$25 + 43k$$ for some integer $$k$$.

**Problem 6:**

Solve each of the following 
* (A) $$x = 5 \mod 11$$, $$x = 14 \mod 29$$, $$x = 15 \mod 31$$,
* (B) $$x = 5 \mod 6$$, $$x =4 \mod 11$$, $$x = 3 \mod 17$$.

**Solution:**

* (A) We propose a solution of the form

$$x = a\cdot 29\cdot 31 + b\cdot 11\cdot 31 + c\cdot 11\cdot 29.$$

Then it must be true that

$$a\cdot 29\cdot 31\equiv 5\mod 11$$

$$b\cdot 11\cdot 31\equiv 14\mod 29$$

$$c\cdot 11\cdot 29\equiv 15\mod 31$$

These equations solve to $$a=2$$, $$b=-2$$, and $$c=12$$, giving us the solution

$$x = 2\cdot 29\cdot 31 - 2\cdot 11\cdot 31 + 12\cdot 11\cdot 29 = 4944.$$

By the Chinese Remainder Theorem, all solutions are of the form

$$x = 4944 + 11\cdot 29\cdot 31\cdot k$$

for some integer $$k$$.

* (B) We propose a solution of the form

$$x = a\cdot 11\cdot 17 + b\cdot 6\cdot 17 + c\cdot 6\cdot 11.$$

Then it must be true that

$$a\cdot 11\cdot 17\equiv 5\mod 6$$

$$b\cdot 6\cdot 17\equiv 4\mod 11$$

$$c\cdot 6\cdot 11\equiv 3\mod 17$$

These equations solve to $$a=-1$$, $$b=5$$, $$c=7$$, giving us the solution

$$x = -11\cdot 17 + 5\cdot 6\cdot 17 + 7\cdot 6\cdot 11 = 785.$$

By the Chinese Remainder Theorem, all solutions are of the form

$$x = 785 + 6\cdot 11\cdot 17\cdot k$$

for some integer $$k$$.

**Problem 7:** (Brahmagupta, 7th century A.D.)

When eggs in a basket are removed 2,
 3, 4, 5, 6 at a
time there remain, respectively, 1, 2, 3, 4, 5 eggs. When they are taken out 7 at a time,
none are left over. Find the smallest number of eggs that could have been contained in
the basket.


**Solution:**

We are searching for $$x$$ satisfying

$$\begin{align}
x &\equiv 1\mod 2\\
x &\equiv 2\mod 3\\
x &\equiv 3\mod 4\\
x &\equiv 4\mod 5\\
x &\equiv 5\mod 6
\end{align}$$

Note we can't apply CRT right away, since not all the moduli are relatively prime.
The value of $$x$$ modulo $$2$$ and modulo $$3$$ is equivalent to the value of $$x$$ modulo $$6$$, so we can throw out the equation involving modulo $$6$$, since it is redundant.
Moreover, the value of $$x$$ modulo $$4$$ also determines the value of $$x$$ mod $$2$$, so we can also throw out the eqeuation involving modulo $$2$$, since it is also redundant.  This gives use the linear system of congruences.

$$\begin{align}
x &\equiv 2\mod 3\\
x &\equiv 3\mod 4\\
x &\equiv 4\mod 5
\end{align}$$

Now the moduli *are* relatively prime, so we can apply the Chinese Remainder Theorem.
We propose a solution of the form

$$x = a\cdot 4\cdot 5 + b\cdot 3\cdot 5 + c\cdot 3\cdot 4.$$

Then we get the equations

$$\begin{align}
20a &\equiv 2\mod 3\\
15b &\equiv 3\mod 4\\
12c &\equiv 4\mod 5
\end{align}$$

This gives $$a=1$$, $$b=1$$ and $$c=2$$, granting us the solution 

$$x = 4\cdot 5 + 3\cdot 5 + 2\cdot 3\cdot 4 = 59$$.

By the Chinese Remainder Theorem, all solutions ar of the form

$$x = 59 + 3\cdot 4\cdot 5\cdot k$$

for some integer $$k$$, so we see $$59$$ is the smallest possible number of eggs in the basket.

**Problem 8:** (Ancient Chinese Problem.) A band of
 17 pirates stole a sack of gold coins. When they
tried to divide the fortune into equal portions, 3 coins remained.In the ensuing brawl over
who should get the extra coins, one pirate was killed. The wealth was redistributed, but
this time an equal division left 10 coins. Again an argument developed in which another
pirate was killed. But now the total fortune was evenly distributed among the survivors.
What was the least number of coins that could have been stolen?

**Solution:**

According to the gruesome tale, the number of coins $$x$$ satisfies

$$\begin{align}
x &\equiv 0\mod 15\\
x &\equiv 10\mod 16\\
x &\equiv 3\mod 17
\end{align}$$

The first equations says

$$x = 15y$$

for some integer $$y$$.
Therefore $$15y\equiv 10\mod 16$$, which amounts to $$y\equiv -10\equiv 6\mod 16$$.
Thus we have $$y = 6 + 16z$$ for somme integer $$z$$, so that 

$$x=6\cdot 15 + 15\cdot 16z$$.  

Finally the last equation says $$-12+2z\equiv 3\mod 17$$, or rather $$2z\equiv 15\equiv -2\mod 17$$.
Thus we get $$z\equiv -1\mod 17$$, ie. $$z=-1 + 17j$$ for some integer $$j$$.
This gives us the final answer

$$x = 6\cdot 15 + -15\cdot 16 + 15\cdot 16\cdot 17j.$$

By the Chinese Remainder Theorem, all solutions of our system are of this form.
There can't be a negative number of coins, so the least number of coins is the value of $$x$$ when $$j=1$$, ie. $$x=3930$$.



