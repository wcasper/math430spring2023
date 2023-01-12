---
layout: page
title: Extra Credit
permalink: /extras/extra-credit
---

For extra credit, watch the following video and then solve the following problems.

[![3B1B Topology Video Link](http://img.youtube.com/vi/AmgkSdhK4K8/0.jpg)](http://www.youtube.com/watch?v=AmgkSdhK4K8 "3B1B Topology Video")

One of the key parts of the video is when we construct a new topological space by identifying points.  A space like this is called a **quotient space**.

**Problem 1:**
Let $$X$$ be a topological space and let $$\sim$$ be an equivalence relation on $$X$$.
For any $$x\in X$$, let $$[x]$$ denote the equivalence class of $$x\in X$$.

The **quotient space** of $$X$$ with respect to this relation is the set of all equivalence relations on $$X$$, ie

$$X/\sim = \{[x]: x\in X\}.$$ 

Each equivalence class represents the points which are identified or "glued together" in the quotient.

The corresponding **quotient map** is

$$q: X\rightarrow X/\sim,\ \ \ q(x) = [x].$$

* (A) Show that the set

$$\tau = \{U\subseteq X/\sim: q^{-1}(U)\subseteq X\ \text{is open}\}$$

is a topology on $$X/\sim$$.  This is called the **quotient topology**.

* (B) Show that with this topology the quotient map $$q$$ is continuous.


**Problem 2:**
In the video, we consider the unit square $$X = [0,1]\times [0,1]\subseteq \mathbb R^2$$ with the Euclidean topology, along with the relation
defined by setting $$(a,0)\sim (a,1)$$, $$(0,b)\sim(1,b)$$, $$(a,b)\sim (a,b)$$ and $$(a,b)\sim (b,a)$$ for all $$a,b\in [0,1]$$.

* (A) Prove that $$\sim$$ is an equivalence relation on $$X$$.
* (B) Describe a Mobius strip and why it is an interesting object from a geometric or topological point of view.
* (C) Explain why the quotient space $$X/\sim$$ is the same as a Mobius strip, using the video for guidance.

**Problem 3:**
Mathematically, we can realize a Mobius strip more simply as the quotient space $$X/\sim$$ for $$X = [0,1]\times[0,1]$$ the unit square and $$\sim$$ the equivalence relation which says $$(a,b)\sim (a,b)$$ and $$(a,0) \sim (1-a,1)$$ for all $$a,b\in [0,1]$$.

The final argument of the video formally amounts to the following theorem.

**Theorem:** A continuous function

$$f: X/\sim\rightarrow \mathbb{R}\times\mathbb{R}\times [0,\infty)$$

from the M\"{o}bius strip to the upper half of $$\mathbb R^3$$ which sends the boundary of the M\"{o}bius strip into the $$x,y$$-plane cannot be injective.
The reason for this is that an injective function $$f$$ will induce an embedding of two dimensional real projective space $$\mathbb RP^2$$ into $$\mathbb R^3$$.  However, every embedded surface in $$\mathbb R^3$$ can be shown to be **orientable**, but $$\mathbb RP^2$$ is not orientable.  Thus the topological invariant "orientability" shows us no injective functions exist.

* (A) Explain in your own words what it means for a surface to be orientable.
* (B) Explain why a Mobius strip is not orientable.



