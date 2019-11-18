---
title: "Python Tutorial Part 1: Introduction"
draft: true
toc: true
author: Hunter Henrichsen
date: 2019-11-18T20:42:35-06:00
images:
tags:
  - python
  - python-tutorial
---

## Introduction

Programming tends to come off as some sort of nebulous thing, or something out
of a fantasy book. There are people with years of practice called Gurus, strange
words and incantations that run the world, strange titles such as "full-stack,"
"UX," "10X," and all sorts of books that can try and teach you this magic. 

For me, this is how I started off. I found a mentor on YouTube, and followed
along with him. I regarded the concepts that I was being taught as if they were 
magic, and only found interesting pieces. I remember ranting to my brother one 
night, and saying "Why even teach lists? No one would ever use them!" After a 
few years, lists are one of my favorite tools.

In this guide, I hope to convey things first as ideas with examples before
moving into code. I won't go into the setup or installation of python on your
machine, as that tends to be a bit of an arduous process and can be covered
later. Instead, we'll use a few tools that other people have written. First, 
we'll start with a few steps to learn how Python works and some of the cool 
things that it can help you do.  Eventually, we'll move on to making websites 
using Django, and handling data in interesting ways using data structures.

Baby steps, though.

## Setting Up an Editor

To start, we'll set up a place where we can write code. 
[repl.it](https://repl.it) is one site that provides us with a place that we 
can use to write and run python code in our browser. If you click 
[this link here](https://repl.it/languages/python3), it'll automatically set 
you up with a python editor. Any code you write will go in the middle column. 
Your files are on the right, and the output from your code is on the left. We
start off with just one file, main.py. This is the file that will run when you
click the green run button at the top.

My repl looks like this, although yours may differ:

![New Repl.it Project](/img/python-01/ReplStarter.png)

Eventually, we'll get python installed on your computer and have you edit code
there instead of online. Until then, this site will meet our needs.

My repl is available [here](https://repl.it/@hhenrichsen/PythonIntro) if you
wanted to take a look at it.

## Exploring Functions

In a math class, when we talk about a function, we think of something like this:

$$f(x) = x + 3$$

This function `f` takes an input, `x`, and gives us something back. We say what
each thing is when we create the function, and it can be used many times. For
example:

$$f(3) = 6$$
$$f(17) = 20$$

Functions in Python are just like this -- they can take an input and can give 
back an output. This is true of the first function that we're about to use,
named `print`. The `print` function takes as many inputs as we want to give it,
and prints out whatever we give it to the output. 

Try typing this code into the middle portion, and pressing Run:

{{< highlight python "linenos=table,linenostart=1" >}}
print("Hello world!")
{{< / highlight >}}

After it finishes, notice how `Hello world!` apprears on the right side?
Congratulations! You've written your first program!

{{< lessonfooter python 1 >}}
{{< mathjax >}}
