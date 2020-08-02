---
title: "Foundations of Code 2: Functions and Algorithms"
date: 2020-08-02T00:20:38-06:00
draft: false
toc: true
author: Hunter Henrichsen
tags:
  - programming
  - math
summary: Functions and Algorithms are important pieces of writing code. Let's take a look at where they come from, and how they apply to computers.
---

## On Functions

Functions are another important piece of solving problems. In math, these are
normally presented as a problem, something like this:

$$ \textrm{Solve for $f(x) = 2$.} $$
$$ f(x) = x^2 - 1 $$

An analogy that I've heard a few times in math classes is that a function is 
like a box with holes on two opposite sides. Things go in one side and come 
out the other side and they get changed on their way through them. Looking
back through my notes from MATH1050 (Algebra), my professor described it as

> Little people inside of a little black box.

![An excerpt from my notes about functions.](/img/foundations-02/notes.png)

Looking at $f(x) = \dots$, there are a few key pieces there, alluded to above.
$f$ is the name of the function, and just like a variable it's how we refer
to it. $x$ is the input, and is the name of a variable. If we write 
$f(x) = x + 5$, $f(5)$ is not defining a new function, but instead telling us
that we should replace $x$ in that equation with $5$ and get back the result.
If we were to write $y = f(5)$, we could also say that $y = 10$.

A little further into Math, you might run into multivariable functions, 
something like this:

$$ f(x, y) = x + y $$

When I saw this, I needed to reevaluate my definition of a function. Instead
of a name for the variable in the parenthesis, it's a list of variables that
are needed to complete the work inside of a function. And if there are two,
there can be three, four, and many more.

Functions can be combined and reference other functions. $f(x)$ can be
defined as $g(x) + h(x)$ where both of those have separate instructions.
Functions can also be composed together, like $f \circ g = f(g(x))$

## On Algorithms

There's another important concept in Math that's called an **Algorithm**.
Algorithms are a list of steps that are used to get a desired outcome. If
you've ever FOILed two polynomials (First, Outside, Inside, Last), you've
used an algorithm, the same with PEMDAS for the order of operations
(Parenthesis, Exponents, Division/Multiplication, Addition/Subtraction).

These are super similar to functions in that they have an input (be that
an equation, a polynomial, a number), and output (another polynomial,
another number) based on the steps completed.

## Functions for Computers

Functions (called Methods in certain contexts) are used everywhere in code.
There's even a whole style of programming called Functional Programming that's
dedicated to solving problems exclusively using functions.

Functions have three pieces, just like in math. First, they have
**Parameters**, which are a list of variable names that are needed to
complete the work in the function. It can be completely empty, or have many,
many parameters. Second, they have **Outputs** which come from **Return**
instructions. In between, they have a list of instructions that tell a
computer what steps are needed to complete the process. This too can be 
anywhere from one instruction to many. Functions can be used to divide work
up into little pieces and then strung together into larger pieces of work.

{{< serial foundations 2 >}}
{{< mathjax >}}