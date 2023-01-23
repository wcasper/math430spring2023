---
layout: page
title: Mathematical induction
---

>A woman in liquor production
>
>Owns a still of exquisite construction.
>
>The alcohol boils
>
>Through magnetic coils.
>
>She says that it's "proof by induction."

Mathematical induction is an incredibly powerful tool that we can use to prove various mathematical statements.
We will rely on it frequently in this class, so it is worth your time to understand it in and out!

Think of induction like a sequence of mathematical dominos.

<p align="center"><img src="fig/dominos.jpeg"/></p>

In the real world, if you dominos are all close enough together and you knock over the first one, then all the dominos will fall down.
Mathematically, we replace our line of dominos with a sequence of logical statements $$P(0),P(1),P(2),\dots$$ each of which may be true or false.
For example, $$P(k)$$ could be the statement

$$P(k):\quad \sum_{j=0}^kj = \frac{k(k+1)}{2}.$$

Showing the dominos are close enough together is proving that if $$P(k)$ is true, then $$P(k+1)$$ is also true.
Then knocking over the first domino is the same as proving that $$P(0)$$ is true.
Once both of these are done, we know $$P(k)$$ is true for all $$k$$, 

## Principal of Induction

The prototypical inductive proof goes as follows.
1. First state at the beginning of the proof you will be using induction.
2. Next prove that the statement $$P(0)$$ is true.  This is often called proving the **base case**.
3. Now let $$n\geq0$$ be a fixed integer and assume $$P(n)$$ is true.  This is called the **inductive assumption** and should be labeled as such in the proof.
4. Using the inductive assumption, prove that $$P(n+1)$$ must be true.
5. Lastly, state that by the principle of induction $$P(k)$$ is true for all $$k\geq 0$$.

Here's an example.

**Theorem:**

$$\sum_{j=0}^kj = \frac{k(k+1)}{2}.$$

**Proof:**

We will prove this by mathematical induction.

First note that if $$k=0$$, then the sum on the left hand side is $$0$$ and the expression on the right hand side is also zero.  Therefore the statement is true for $$k=0$$.

Let $$n\geq 0$$.  As an inductive assumption, assume that the statement of our theorem holds for $$k=n$$, ie.

$$\sum_{j=0}^nj = \frac{n(n+1)}{2}.$$

Then by our inductive assumption,

$$\begin{align*}
\sum_{j=0}^{n+1}j
  & = (n+1) + \sum_{j=0}^nj\\
  & = (n+1) + \frac{n(n+1)}{2}\\
  & = \frac{2(n+1)+n(n+1)}{2} = \frac{(n+2)(n+1)}{2}.
\end{align*}$$

This shows that the statement of our theorem holds for $$k=n+1$$.
Thus by the principle of induction, the statement of the theorem holds for all $$k\geq 0$$.
:black_square_button:

:warning: **Watch the base case**:  Sometimes the base case might be $$P(1)$$ or $$P(2)$$, or you may have to prove the first few $$P(j)$$'s individually as the base case.

## Strong Induction

For some proofs, we will require an even stronger form of induction, aptly called **strong induction**.
It works just like the usual principle of induction, except that the inductive assumption changes.
Instead of assuming that $$P(n)$$ is true for some $$n$$, we assume that $$P(k)$$ is true for all $$0\leq k\leq n$$.

Here's an example, based on the sequence of **Fibonacci numbers** defined by $$F_1=1$$, $$F_2=1$$, $$F_3=2$$, $$F_4=3$$, and more generally by

$$F_{k+2} = F_{k+1} + F_k,\quad \forall\ k\geq 0.$$

**Theorem:**
The $$k$$'th Fibonnaci number can be expressed in terms of the **Golden Ratio** $$\varphi = \frac{1+\sqrt{5}}{2}$$ and its conjugate $$\psi = \frac{1-\sqrt{5}}{2}$$ by

$$F_k = \frac{\varphi^k-\psi^k}{\varphi-\psi}\quad\forall\ k\geq 1.$$

**Proof:**
We will prove this theorem by strong induction.

First note that if $$k=1$$, the numerator on the right hand side is equal to the denominator, so $$F_1 = 1$$.
Likewise, if $$k=2$$ the expression on the right hand side simplifies to $$\varphi+\psi=1$$.
Thus the statement of the theorem holds for $$k=1,2$$.

Let $$n\geq 2$$.  As an inductive assumption, assume that the statement of our theorem holds for all $$1\leq k\leq n$$.
In other words, assume

$$F_k = \frac{\varphi^k-\psi^k}{\varphi-\psi},\quad\forall\ 0\leq k\leq n.$$

Then in particular our inductive assumption states

$$F_{n-1} = \frac{\varphi^{n-1}-\psi^{n-1}}{\varphi-\psi},\quad\text{and}\quad F_{n} = \frac{\varphi^{n}-\psi^{n}}{\varphi-\psi}.$$

It follows that

$$\begin{align*}
F_{n+1}
  &= F_n + F_{n-1}\\
  &= \frac{\varphi^{n-1}-\psi^{n-1}}{\varphi-\psi} + \frac{\varphi^{n}-\psi^{n}}{\varphi-\psi}\\
  &=\frac{\varphi^{n-1}-\psi^{n-1}+\varphi^{n}-\psi^{n}}{\varphi-\psi}\\
  &=\frac{\varphi^{n-1}(1+\varphi)-\psi^{n-1}(1+\psi)}{\varphi-\psi}
\end{align*}$$

Now note that both the golden ratio and its conjugate are roots of the quadratic polynomial $$x^2-x-1$$, and therefore $$\varphi^2=\varphi+1$$ and $$\psi^2=\psi+1$$.
Inserting this in the previous expression, we see

$$F_{n+1} = \frac{\varphi^{n-1}\varphi^2-\psi^{n-1}\psi^2}{\varphi-\psi} = \frac{\varphi^{n+1}-\psi^{n+1}}{\varphi-\psi}.$$

Therfore by the principle of strong induction, our theorem is true for all $$k\geq 1$$.
:black_square_button:



