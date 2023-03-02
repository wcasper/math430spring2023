---
layout: page
title: Linear congruence
---

A **linear congruence** is an equation of the form

$$ax\equiv b\mod n.$$

Here, $$a$$ and $$b$$ are known and we are searching for the values of $$x$$ satisfying this equation, of which there will be at most finitely many modulo $$n$$.
Just like with Diophantine equations, solutions need not exist!

**Example:** There are no solutions of $$2x\equiv 1\mod 4$$.

In fact, there is a pretty straightforward connction between linear congruence and linear Diophantine equations.
Specifically $$ax\equiv b\mod n$$ if and only if for some integer $$y$$

$$ax + ny = b$$

Thus we are able to apply our theory of linear Diophantine equations to this situation.

**Theorem:** The linear congruence $$ax \equiv b\mod n$$ has a solution if and only if $$\gcd(a,n)$$ divides $$b$$.
In this case, there are exactly $$d$$ different solutions up to congruence modulo $$n$$.

**Proof:**

Let $$d = \gcd(a,n)$$.

Finding a solution of $$ax\equiv b$$ is equivalent to finding a solution of the linear Diophantine equation  $$ax+ny = b$$.
Thus a solution exists if and only if $$d\mid b$$.

Suppose that $$x=x_0$$ satisfies $$ax\equiv b$$.
Then $$x=x_0 + t\frac{n}{d}$$ is also a solution for all $$0\leq t < d$$.
This gives us $$d$$ different solutions, none of which are congruent modulo $$n$$.

Conversely, suppose $$x=x_1$$ is any solution.
Then there exist integers $$y_0, y_1$$ with the property that $$x=x_i$$ and $$y=y_i$$ satisfies $$ax+ny = b$$ for both $$i=1,2$$.
Furthermore, all solutions of the linear Diophantine equation are of the form

$$x = x_0 + t\frac{n}{d},\quad y = y_0 - t\frac{a}{d}.$$

This in particular implies  $$x_1 = x_0 + t\frac{n}{d}$$, so up to modulus $$n$$ it is one of the solutions already discussed.
:black_square_button:

Since the congruence classes modulo $$n$$ are determined by integers $$0\leq r < n$$, an alternative formulation tells us that there will be $$d$$ nonnegative solutions less than $$n$$.

## Solving linear congruences

Now that we know how many solutions of a linear congruence equation there are, it remains to determine exactly how one might find them.
The proof of the previous theorem suggests that one possible answer is to exchange the problem for the corresponding linear Diophantine equation, and then apply the Euclidean algorithm.  This works fine, but we can alternatively formulate a different strategy using *multiplicative inverses*.

**Definition:** A **multiplicative inverse** of $$a$$ modulo $$n$$ is a number $$c$$ with $$ac = 1\mod n$$.

From the previous theorem, we see that $$a$$ has a multiplicative inverse modulo $$n$$ if and only if $$\gcd(a,n) = 1$$.

To see how to apply multiplicative inverses to our situation, suppose $$ax\equiv b\mod n$$ has a solution.
Then this means $$d=\gcd(a,n)$$ must divide $$b$$, as well as $$a$$ and $$n$$, meaning we can reduce our problem to

$$(a/d)x = (b/d)\mod (n/d).$$

Now $$a/d$$ and $$n/d$$ are relatively prime, so $$a/d$$ has a multiplicative inverse $$c$$ modulo $$n$$ which we can find via trial and error.
Multiplying both sides of our reduced equation by the multiplicative inverse, we get

$$x = (bc/d)\mod (n/d).$$

Consequently our solution must be of the form $$x = bc/d + t(n/d)$$ for some integer $$t$$.  We can then search for the integer in question.

**Example:**  Solve the linear congruence $$25x = 15\mod 29$$.

**Solution:**  Since $$29$$ is prime, $$\gcd(25,29)=1$$ and so $$25$$ has a multiplicative inverse modulo $$29$$.  In particular $$25\equiv -4$$, so $$25\cdot 7\equiv -28\equiv 1$$.  Thus  $$7$$ is a multiplicative inverse of $$25$$ modulo $$29$$ and

$$x = 7\cdot 15 \equiv 18\mod 29.$$

This is the only solution up to congruence modulo $$29$$.




