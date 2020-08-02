---
title: "Foundations of Code 1: Variables"
draft: false
toc: true
author: Hunter Henrichsen
date: 2020-08-01T22:34:26-06:00
tags:
  - programming
  - math
---

## Series Introduction
Many people try to start tutorials on coding with code. I know that I've been
one of those, and will only allude to the fact that Computer Science is based
in Math. Anyone who has been in an Algebra class will draw that line. The
thing is, Math isn't required to start learning to program. Some of the
concepts are useful, yes, but those can be learned independently.

I was one of those who learned how to write code without taking math much
further than Algebra, and now I'm comfortable teaching others how to write
code, and you can be too. To that end, I'm starting up this series to try and
bridge the gap and make it easier to understand the concepts that carry over.
This should be the first step or a good refresher to see where the concepts
come from. So let's get started, and talk about variables.

And don't be afraid if you've not seen much math, haven't worked with it in 
awhile, or if it intimidates you -- I try to keep my examples simple, and 
only talk about the relevant parts.

## What are Variables
When you start learning about math, you start with operations. Adding,
subtracting, multiplying, and dividing come first, with exponentials and
roots soon following. Once we have a good grasp on these, we're introduced to
a new type of puzzle: variables. They start out simple, with things looking
like this:

$$ \textrm{Solve for $x$.} $$ 
$$ 10 + x = 15$$

Where we find out that $x = 5$ by subtracting the $10$ over to the other side.
Then we move on to more complex equations:
$$ \textrm{Solve for $x$.}$$ 
$$ x^2 - 1 = 0$$

Where we find that $x$ *could be* equal to either $1$ or $-1$ using any number
of techniques -- factoring, the quadratic formula, graphing, etc.

And just like that, we've covered something important. Yes, we can move
equations around until they're in a form we like, but the important piece is
that $x$ *has a value*. This has some important implications if we're
thinking about a system of linear equations like this:

$$ \textrm{Solve for $x$ and $y$.} $$
$$ x + y = 5 $$
$$ x + 1 = y $$

Once we figure out what $x$ is, every place where $x$ happens in the problem
can be replaced with the value of $x$, and the same for $y$:

$$ \textrm{Solve for $x$ and $y$.} $$
$$ 2 + y = 5 $$
$$ 2 + 1 = y $$

The fact that these have values is what allows us to solve a problem, and
that's not only true for this problem, but many of the problems that are
faced when coding. Storing data and moving it around in a computer is much
easier when we can clearly name them.

## Variables for Computers

Computers are really good at keeping track of values. The interesting thing
is that this doesn't only apply to numbers. Computers can just as easily say
$x = $ `Hello!`, or $x = 15.2$, and work with them in the same way. Keeping
track of these is really easy for computers, and they can quickly find where
$x$ lives and update its value.

Depending on the language you're working in, you can even mix between
different things. One minute, $x$ can be a bunch of text and the next it can
be a decimal value. Other languages are more strict about this, and say that
in order to be safe, we say what $x$ is allowed to be and stick to it. Both
have benefits and drawbacks. If you're using the other guides on this site,
**Python** is the type that lets you store anything, and **Java** is the type
that's more strict.

The other benefit that we have in computers is that we're not limited to
single characters. We can name something `helloMessage` instead of just $x$.
This makes communication clearer when reading through a piece of code, as
well as when working with functions.

As always, thanks for reading. If you have questions or suggestions, join me
on [Discord](https://discord.gg/jMQ8gsF).

{{< serial foundations 1 >}}
{{< mathjax >}}