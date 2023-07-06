---
title: "Probability an integer is a fraction"
description: "probability behind mathlify's generateRandomFrac() method"
date: 2023-06-04T05:00:00Z
image: "/images/posts/01.jpg"
categories: ["probability"]
authors: ["Kelvin Soh"]
tags: ["mathlify", "generateRandomFrac"]
draft: false
---

We are given a fraction $f = \frac{n}{d}$, such that the non-zero numerator $n$ satisfies $-9 \leq n \leq 9$ and
the denominator $d$ satisfies $1 \leq n \leq 9$. How many of these fractions $f$ are integers?

## Counting by cases

### Case 1: $d = 1$

There are 18 possible cases.

### Case 2: $|n|=d$

There are 16 additional cases (18 in total but with an overlap of 2 with case 1).

### Case 3: $d=2$

There are 6 cases ($n=\pm 4, \pm 6, \pm 8$)

### Case 4: $d=3$

There are 4 cases ($n=\pm 6, \pm 9$)

### Case 5: $d=4$

There are 2 cases ($n=\pm 8$)

## Results

The total cases add up to $\boxed{46},$ leading to a probability of
$\boxed{\frac{8}{27}\approx 0.284}$ that the `getRandomFrac` function,
given the default parameters, will return an integer.
