---
layout: page
title: Early number theory
---

Originally, number theory was simply called *arithmetic*, and has origins that can be traced as far back as ancient Egypt and Babylon.
That being said, our knowledge of the formal theory of arithmetic starts much later in ancient Greece with Pythagoras.

After studying in Egypt himself, Pythagoras returned to Greece and created his own school studying, among other things, number theory.
His students called thmselves Pythagoreans, and believed that the study of whole numbers was the key to understanding the world.
For this reason, the study of numbers often found itself intertwined with philosophy and mysticism.


## Triangular numbers

The $$n$$'th **triangular number** $$t_n$$ is the number of objects that you can arrange into a grid in the shape of an equilateral triangle with $$n$$ objects on each side.

<p align="center"><img src="fig/trianglenum.png"/></p>

In other words, the $$n$$'th triangular number is the sum of the integers $$1 + 2 + \dots + n$$.
Triangular numbers were studied by the Pythagoreans, woh first found an explicit formula for the $$n$$'th triangular number

$$t_n = \frac{n(n+1)}{2}.$$

Gauss is also famously said to have rediscovered this formula as a child.  The formula can be proved in many ways, including inductively or geometrically.

Triangular numbers have some interesting properties, such as the following.

**Theorem (Plutarch, 100AD)**: An integer $$m>0$$ is a triangular number if and only if $$8m+1$$ is a perfect square.

**Theorem (Nicomachus, 100AD)**: The sum $$t_n+t_{n+1}$$ is a perfect square for all $$n\geq 1$$.

## Perfect numbers

Another kind of whole number considered by the ancient Greeks is a perfect number.  A **perfect number** is a number which is equal to the sum of all of its proper divisors.

**Example:** The divisors of $$6$$ are $$1$$, $$2$$, and $$3$$.  Since $$6 = 1 + 2 + 3$$, we see that $$6$$ is a perfect number.

**Example:** The divisors of $$28$$ are $$1$$, $$2$$, $$4$$, $$7$$, and $$14$$.  Since $$1+2+4+7+14=28$$, this is also a perfect number.

The first four perfect numbers are $$6$$, $$28$$, $$496$$, and $$8128$$.
Some basic facts about perfect numbers remain today as open problems.

**Unsolved Problem 1:** Are there any odd perfect numbers?

**Unsolved Problem 2:** Are there infinitely many perfect numbers?

As of January 2023, there are only $$51$$ known perfect numbers.

**Question:** Are the first four perfect numbers also triangular?

<details>
  <summary>Click for answer.</summary>
  Yes!  To check this, multiply each by $$8$$ and add $$1$$.  The number that we get is a perfect square each time.
</details>



