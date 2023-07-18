---
title: H2 Math 2022 Paper 1 Question 1 Superset
description: "specifications for the H2 Math 2022 Paper 1 Question 1 Modification"
date: 2023-07-06T05:00:00Z
image: "/images/posts/02.jpg"
categories: ["specifications"]
authors: ["Kelvin Soh"]
tags: ["tys", "complex numbers", "math-cat", "h2 math", "2022 Paper 1"]
draft: false
---

H2 Math 2022 Paper 1 Question 1 is a question about solving a set of linear simultaneous
equations in two unknowns over the complex numbers. In general, the question is of the
form

$$
\begin{align*}
\alpha_1 z + \beta_1 w &= \gamma_1 \\
\alpha_2 z + \beta_2 w &= \gamma_2
\end{align*}
$$

## Modifications for simpler solution working

While the above can be solved as long as $\alpha_1 \beta_2 - \alpha_2 \beta_1 \neq 0$,
the procedure can get quite messy with many real and complex parts. Hence we propose to
generalize the question to a smaller scope, namely equations of the form

$$
\begin{align*}
a_1 \mathrm{i}z + b_1 w &= c_1 \\
\alpha_2 z + b_2 \mathrm{i}w &= \gamma_2
\end{align*}
$$

where $a_1, b_1, b_2, c_1 \in \mathbb{Z}\setminus \{0\}$.

## Generated variables

Let $z = x_1 + \mathrm{i}y_1, w = x_2 + \mathrm{i}y_2$ and $\alpha_2 = x_3 + \mathrm{i}y_3$.

To generate the variables for a question, we first generate $\boxed{a_1, b_1}$. The criteria
that $c_1 \in \mathbb{R}$ means that we arrive at the Diophantine equation

$$
a_1 x_1 + b_1 y_2 = 0.
$$

We will take the trivial solution $x_1 = \pm b_1, y_2 = \mp a_1$.

We then proceed to generate the rest of the variables $\boxed{y_1, x_2, x_3, y_3, b_2}$. $c_1$ and
$\gamma_2$ can then be calculated.

## Generation constraints

We place constraints on the variables to ensure that

1. the equation is solvable
2. we don't end up with overly big numbers that could be difficult to work with

Point 1 is relatively simple: as long as $\alpha_2 \not \in \mathbb{R}$, the equation is solvable
due to the other constraints already in place that the other coefficients are real/purely imaginary.

For point 2, we will ideally like to have $\lVert z \rVert|_\infty$ for all numbers in the question
(ie $\alpha_i, \beta_i, \gamma_i, z, w$ in the original formulation). However, while trying to balance this
against the desire for a wide range of numbers and the ease of generation, we have settled on generating
the variables such that

1. $1 \leq |a_1| \leq 2$
2. $2 \leq |b_1| \leq 3$
3. $0 \leq |x_2| \leq 2$
4. $1 \leq |y_1| \leq 2$
5. $1 \leq |x_3|, |y_3| \leq 2$
6. $1 \leq |b_2| \leq 2$

Under these constraints, applying the triangle inequality to equation 1
gives as a bound of $|c_1| \leq \sqrt{13} + 3 \sqrt{5} \approx 10.3$. Meanwhile, equation 2
gives us $|\gamma_2| \leq \sqrt{5}\sqrt{13} + 2\sqrt{5} = 12.5$.

## Possible combinations

Our current implementation generates $\boxed{7128}$ unique questions, of which
$450$ ($\approx 6.3\%$) have infinity norm bigger than 9. Interesting, the upper bound of
$|\gamma_2| = 12$ was reached but the maximum $|c_1|$ value observed was only 8.
