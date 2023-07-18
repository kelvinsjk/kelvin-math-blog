---
title: Math Cat SLE Example 1
description: "specifications for the Math Cat SLE Example 1"
date: 2023-07-19T06:00:00+00:00
image: "/images/posts/03.jpg"
categories: ["specifications"]
authors: ["Kelvin Soh"]
tags: ["h2 math", "math-cat", "equations"]
draft: false
---

In this example, we will ask students to solve for a quadratic function $f(x)$, given two points
$(x_1, f(x_1))$, $(x_2, f(x_2))$ and the gradient at $x_1$.

## Ensuring unique solution

We will be able to form the following system of linear equations in $a,b$ and $c$:
$$
\begin{align}
x_1^2 a + x_1 b + c &= f(x_1) \\
x_2^2 a + x_2 b + c &= f(x_2) \\
2x_1 a + b &= f'(x_1)
\end{align}
$$

The determinant of the coefficient matrix simplifies to
$$
(x_2 - x_1)^2
$$
so we just have to ensure that $x_1 \neq x_2$.

## Generated variables

We will generate the following variables:

- $a$: $\pm (1 \text{ to } 5)$
- $b$: $\pm (0 \text{ to } 5)$
- $c$: $\pm (1 \text{ to } 5)$
- $x_1, x_2$: $\pm (1 \text{ to } 5)$ where $x_1 \neq x_2$
