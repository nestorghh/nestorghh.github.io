---
layout: post
title: "Motivating Gradient Descent"
date: 2023-07-11
---

Gradient descent is the main optimizer used to solve for the objective function in many machine learning algorithms. In this post,
I will motivate a family of iterative optimization algorithms and we will see that gradient descent is just a  particular case or base case under this framework.

We will start with the following lemma:

Let $f: \mathbb{R}^{n} \rightarrow \mathbb{R}$ be a continously differentiable function in an open region $D \subset \mathbb{R}^{n}$. For all $x \in D$ and $p \in \mathbb{R}^{n}$,
the directional derivative in the $p$ direction, defined by 

$$
  \frac{\partial f}{\partial x} = \lim_{\epsilon \to 0 } \frac{f(x+\epsilon p) - f(x)}{\epsilon} 
$$

exists and is equal to $\nabla f(x)^T \cdot p$

Proof:

Given $x$ and $p$, let us define the scalar function $g(t) = f(x+tp)$. Since $f$ is continously differentiable in $D$, the function $g: \mathbb{R} \rightarrow \mathbb{R}$ is also 
continuously differentiable. In fact,

$$
g'(t) = \lim_{\epsilon \to 0} \frac{g(t+\epsilon) - g(t)} {\epsilon} = \lim_{\epsilon \to 0} \frac{f(x+(t+\epsilon)p)-f(x+tp)}{\epsilon} 
$$

On the other hand, by using the chain rule we have:

$$
g'(t) = \sum_{i=1}^{n} \frac{\partial f(x)}{d}
$$
