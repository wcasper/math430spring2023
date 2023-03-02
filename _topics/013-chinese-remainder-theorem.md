---
layout: page
title: Chinese remainder theorem
---

The study of systems of linear congruences can be traced as far back as the 1st century A.D. in thee work of Sun-Tsu.

**Question:** Find a number that leaves the remainders 2, 3, 2 when divided by 3, 5, 7, respectively.

In terms of congruences, this is equivalent to trying to solve the three simultaneous equations

$$\begin{align}
x\equiv 2\mod 3
x\equiv 3\mod 5
x\equiv 2\mod 7
\end{align}$$

As a nod toward the history of puzzles like this, the following theorem is called the Chinese Remainder Theorem.

**Chinese Remainder Theorem:**

Let $$n_1,n_2\dots, n_r$$ be a sequence of pairwise relatively prime positive integers (ie. $$\gcd(n_j,n_k) = 1$$ for $$j\neq k$$).
Then for any integers $$a_1,\dots a_r$$ the system of linear congruences

$$\begin{align}
x\equiv a_1\mod n_1\\
x\equiv a_2\mod n_2\\
x\equiv a_3\mod n_3\\
\dots\\
x\equiv a_r\mod n_r\\
\end{align}$$

has a simultaneous solution, which is unique modulo $$n_1n_2\dots n_r$$.

**Proof:**

Let $$n = n_1n_2\dots n_r$$.
Our idea is to look for a solution of the form

$$x = x_1\frac{n}{n_1} + x_2\frac{n}{n_2} + \dots + x_r\frac{n}{n_r}.$$

Since $$\frac{n}{n_j}$$ is divisible by $$n_k$$ for all $$k\neq j$$, such an expansion of $$x$$ would have the specific property that

$$x = x_k\frac{n}{n_k}\mod n_k.$$

Thus $$x$$ will be a solution if we can simply choose $$x_k\frac{n}{n_k} \equiv a_k\mod n_k$$.

This is an equation that we can solve!  In particular, $$n_k$$ $$n/n_k$$ are relatively prime and therefore for each $$k$$ we can find a multiplicative inverse $$u_k$$ satisfying $$u_k(n/n_k) = 1\mod n_k$$.  Then $$x_k = a_ku_k$$ satisfies $$x_k\frac{n}{n_k} \equiv a_k\mod n_k$$.

It follows that

$$x = a_1u_1\frac{n}{n_1} +  a_2u_2\frac{n}{n_2} + \dots + a_nu_n\frac{n}{n_r}$$

is a simultaneous solution of our system of equations.

Now to show that this solution is unique modulo $$n$$, suppose that $$x=y$$ and $$x=z$$ are two solutions of the above system of linear congruences.
Then $$y-z\equiv 0\mod n_k$$ for all $$k$$.
This implies that $$n_k \mid (y-z)$$ for all $$k$$.
Since the $$n_k$$ are relatively prime, it follows that $$n \mid (y-z)$$.  Hence $$y\equiv z\mod n$$.

:black_square_button:

In particular, the proof the Chinese remainder theorem gives us a specific solution of the system of linear congruences

$$x = a_1u_1\frac{n}{n_1} +  a_2u_2\frac{n}{n_2} + \dots + a_nu_n\frac{n}{n_r},\quad\text{where} u_k\frac{n_1n_2\dots n_r}{n_k}\equiv 1\mod n_k.$$

Thus for example, we should be able to find a solution of Sun Tsu's puzzle, unique up to $$105$$.

$$\begin{align}
x\equiv 2\mod 3
x\equiv 3\mod 5
x\equiv 2\mod 7
\end{align}$$

Specifically, in this case $$n = 105$$, we want

$$35u_1 \equiv 1 \mod 3,\quad 21u_2\equiv 1\mod 5,\quad 15u_3\equiv 1\mod 7.$$

This is accomplished with $$u_1 = 2$$, $$u_2 = 1$$, and $$u_3 = 1$$, giving us the solution

$$x = 2\cdot 2\cdot 35 + 3\cdot 1\cdot 21 + 2\cdot 1\cdot 15 = 233.$$

This isn't the only solution.  In fact, if we add any multiple of $$105$$ to it, we get a simpler solution, namely $$233-2\cdot 105 = 23$$.


The Chinese remainder theorem also helps us to break down linear congruence problems into systems of smaller problems.

**Example:**  Solve the linear equation $$17x=9\mod 276$$.

**Solution:** We can write $$276 = 3\cdot 4\cdot 23$$, so that

$$\begin{align}
2x &\equiv 0\mod 3\\
x  &\equiv 1\mod 4\\
17x&\equiv 9\mod 23
\end{align}$$

The first equation says $$x = 3k$$ for some integer $$k$$.
The second equation then tells us

$$3k\equiv 1\mod 4$$

Multiplying both sides by $$3$$, we get $$k\equiv 3\mod 4$$, ie. $$k=3+4j$$.  Hence $$x = 9 + 12j$$.

Now putting this into the last equation, we see $$3j\equiv 6\mod 23$$, which reduces to $$j\equiv 2\mod 23$$.
Hence $$j = 2 +23t$$ and $$x = 33 + 276t$$.
:black_square_button:


## A geometric analogy

The Chinese Remainder Theorem can be understood intuitively from a geometric point of view.
We think of the set $$X$$ of all prime numbers abstractly as a sort of analog of the real line.
The idea then is to think about various integers as functions on $$X$$, analogous to the way we think about polynomials on $$\mathbb{R}$$.
From this point of view, an integer $$n$$ is replaced by the *residue function*

$$f_n: X\rightarrow \mathbb{Z},\quad p\mapsto n\mod p.$$

The function $$f_n$$ vanishes at a point $$p$$ if and only if $$p$$ divides n$$.

Pushing this analogy even further, we can think of the value of $$n\mod p^k$$ as something like the Taylor series expansion of $$f_n$$ at $$p$$ up to order $$k$$.
The Chinese Remainder Theorem tells us that we can find a solution of 

$$\begin{align}
x\equiv a_1\mod p_1^{k_1}\\
x\equiv a_2\mod p_2^{k_2}\\
\dots\\
x\equiv a_r\mod p_r^{k_r}\\
\end{align}$$

From our analogy, this is akin to obtaining a polynomial with prescribed Taylor series expansions at certain points in the real line.

**Example:** Find a polynomial $$f(x)$$ whose value is $$3$$ at $$x=-1$$, $$1$$ at $$x=0$$, $$-2$$ at $$x=1$$,  and $$4$$ at $$x=5$$.

**Solution:**

One way to do this is to set up a big linear system of equations for the arbitrary coefficients of a polynomial of degree $$3$$ and then solve it.
Alternatively, we can think about a polynomial of the form

$$f(x) = a x(x-1)(x-5) + b(x+1)(x-1)(x-5) + c(x+1)x(x-5) + d(x+1)x(x-1)$$

This has the advantage that $$f(-1) = -12a$$, $$f(0) = 5b$$, $$f(1) = -8c$$, $$f(5) = 120d$$, which allows us to immediately find $$a,b,c,d$$

$$f(x) = \frac{-3}{12} x(x-1)(x-5) + \frac{1}{5}(x+1)(x-1)(x-5) + \frac{1}{4}(x+1)x(x-5) + \frac{1}{30}(x+1)x(x-1)$$

We can get more solutions by adding on any polynomial which vanishes at $$-1,0,1,5$$, ie. anything of the form $$g(x)(x+1)x(x-1)(x-5)$$.
:black_square_button:

Notice this is the same idea in spirit of the Chinese Remainder Theorem.

**Example:** Find a number $$n$$ whose value is $$2\mod 3$$, $$3\mod 5$$ and $$1\mod 7$$.

**Solution:**

We want $$f_n(3) = 2$$, $$f_n(5)=3$$ and $$f_n(7) = 1$$.
We can think about an integer of the form

$$n = a\cdot 5\cdot 7 + b\cdot 3\cdot 7 + c\cdot 3\cdot 5.$$

Then $$f_n(3) = 35a\mod 3 = 2a\mod 3$$, $$f_n(5) = 21b\mod 5 = b\mod 5$$ and $$f_n(7) = 15c\mod 7 = c\mod 7$$.
Right away, we get $$a=1$$, $$b=3$$ and $$c=1$$ so that 

$$n = 1\cdot 5\cdot 7+ 3\cdot 3\cdot 7 + 1\cdot 3\cdot 5 = 113$$

Is a solution.  We can get more solutions by adding on any multipl of $$3\cdot 5\cdot 7 = 105$$.  In particular $$113-105 = 8$$ is also a solution.



