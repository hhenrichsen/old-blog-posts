---
title: "Java Tutorial Part 2: Variables"
date: 2019-08-05T02:12:56-06:00
draft: false
toc: true
images:
author: Hunter Henrichsen
tags:
  - java
  - java-tutorial
---

## Overview

Today we're going to look at how we can keep track of things in Java, and the
different things that are available for keeping track of those different things.

This lesson starts off a little theoretical, just because there's some important
information to be shared on which types of things you can keep track of.

## Types

Java is a strongly typed language. That means that every variable needs to know
what type of thing it is. Since every variable needs to know what type it is, we
need to tell them what type they are. 

Java has a collection of basic types, called **Primitives**:

### The Boolean Type

`boolean` is the smallest of the primitive types. It keeps track of whether
something is `true` or `false`. These are like light switches, they can only be
on or off. These are the size of a **Bit** in memory, which is a single `1` or
`0`, but how exactly they're stored is not specified by the Java language. 

### Integral Types

`byte` is the next smallest of the primitive types, and the smallest of the
Integral primitives. Integral types are types that store whole numbers. Bytes
are numbers between -128 and 127. It is stored as 8 bits in memory, or 8 `1`s or
`0`s. 

`short` is the second smallest integral primitive. `Short`s are numbers between
-32,768 and 32,767. Shorts are made up of two bytes, or 16 bits.

`int`, or Integer, is the third smallest integral primitive. These are the most
commonly used to represent whole numbers. Integers are numbers between
-2,147,483,648 and 2,147,483,647, and are made up of four bytes.

`long` is the largest integral primitive. These are used to store large numbers,
from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807. Longs are made up
of 8 bytes. Longs are suffixed by L, such as `12L`.

`char` is the last integral type, but it's a bit of a special case. Chars are
used to represent characters, such as `a` (97), `5` (53), `A` (65), `!` (33),
and ` ` (32). These are all based on their ASCII and Unicode values[^1]. These
are 2 bytes long, just like shorts, but these can go up to 65535, or '\uFFFF'.
Characters are surrounded by single quotes (`'`).

[^1]: A table of ASCII values can be found [here](http://www.asciitable.com/).

### Floating Point Types

`float` is the smallest of the floating point types. Floating point types are
approximations of decimals, although they can be innacurate. Floats are stored
in 4 bytes. Floats are suffixed by F, such as `15.3f`. There is no clearly
defined maximum and minimum, although it's approximately 3.4^38.

`double` is the largest of the floating point primitives, and are stored in 8
bytes. Doubles are suffixed by D, such as `22.512d`. There is no clearly defined
maximum, although it's approximatley 1.7^308.

### Classes

There are three types of primitives, but they can be used to build up classes.
One of the most important ones that we've already used is the `String` class.
This contains a list of `char`s that build up longer text. Notice how `String`
is uppercase, and how all of the primitives are lowercase.

Most of what Java has to offer is in the form of Classes. We'll talk about using
other classes and writing our own in a few more tutorials.

That said, let's get into storing some data!

## Storing Data

To start, let's make a new class. I'm going to call this one `Java02`, but you
are free to name it as you like. I'm going to also put another main method in
this one. If you've forgotten, it will look like this:

`Java02.java`
{{< highlight java "linenos=table" >}}
package me.hhenrichsen;

public class Java02 {
    public static void main(String[] args) {

    }
}
{{< / highlight >}}

Now let's create some variables. The first thing that we do is **Declare**
variables, which is to tell Java that "Hey, we want to store some data in this
section, it's going to be of X type and be called Y." 

A declaration looks like this:

{{< highlight java "linenos=table,linenostart=6" >}}
int aNumber;
{{< / highlight >}}

What we just did right there was create an `int` named `aNumber`. Right now it
just has a 0 inside of it, but we can change that by Initializing it.
**Initializing** is when we set the first value that a variable has.

{{< highlight java "linenos=table,linenostart=6" >}}
int aNumber;
aNumber = 15;
{{< / highlight >}}

In this case, we've told Java that `aNumber` is to start out at 15.

These can be combined into a single statement like so:

{{< highlight java "linenos=table,linenostart=6" >}}
int aNumber = 15;
{{< / highlight >}}

Where we both create a new `int` named `aNumber`, and tell it that it should
start out at `15`.

If we want to change what value is stored in a variable, we need to reassign
it. When we change what a variable is, it's called **assigning**. That looks
like this:

{{< highlight java "linenos=table,linenostart=6" >}}
int aNumber = 15;
aNumber = 22;
{{< / highlight >}}

### Operating on Variables

#### Addition

Something super important about this section is that you try things as you see
them. I'm working in `int`s and `Strings`, but what happens if you use `float`s
or `boolean`s? If I show you that you can add two things together, or that you
can use something in place of another, what happens if you use it somewhere
else? What happens if you add three things? Can you subtract in the same way?

A cool thing about variables is that they can be combined into new values.
Let's say we wanted to keep track of how many animals we have in a farm. We'd
start off by creating variables for each of the individual animals:

{{< highlight java "linenos=table,linenostart=6" >}}
int chickens = 30;
int horses = 4;
int cows = 12;
int parrots = 7;
int cats = 22;
{{< / highlight >}}
*It's a weird farm, okay?*

Now say we wanted to keep a total of all of the animals. It'd be nice if
we could tell Java to just add them all together.

{{< highlight java "linenos=table,linenostart=10" >}}
int totalAnimals = chickens + horses + cows + parrots + cats;
{{< / highlight >}}

Well, turns out that that works in Java! We can make Java do all of the work, 
and not have to do the adding ourselves!

Just to check, let's try printing what's stored in `totalAnimals`:

{{< highlight java "linenos=table,linenostart=11" >}}
System.out.println(totalAnimals);
{{< / highlight >}}

We should get 75 printed out to our console, just like we'd expect.

When we print things to our console, though, we should be specific about what
they are. If someone ran our program, they wouldn't know what to do with the 53
that pops out in console.

It turns out that when you add things to Strings in Java, it adds whatever they
are to the message. Let's try creating a message, and then sending that *plus
the number of animals* to the console.

{{< highlight java "linenos=table,linenostart=11" >}}
String message = "Our farm has this many animals: ";
System.out.println(message + totalAnimals);
{{< / highlight >}}

Let's say we wanted to rephrase that, so it sounds more natural, and has the
number in the middle. We could create two message variables, but remember what
we did in the first lesson with "Hello World!". We just told
`System.out.println` a specific message to send, using string literals.

**String Literals**, and literals of any type is text that's typed that
transforms into the code representation of something, like a `String`. The
`"Hello World!"` inside our first program was a string literal, and we can
include literals in any place that a variable works. I listed some other
literals up above, like `12.3f` and `15`. *Anywhere a variable goes, a literal
can go. Anywhere a literal goes, a variable can go.*

{{< highlight java "linenos=table,linenostart=11" >}}
System.out.println("We have " + totalAnimals + " animals on our farm.");
{{< / highlight >}}

Now we get `We have 75 animals on our farm.` which sounds a lot more natural.
Now try changing one of the amounts and running the program again. The number
should change based on what you give it.

Now lets say we get two more cats. We could update the variable again, but we
can also make Java do the work of keeping track of everything. 

{{< highlight java "linenos=table,linenostart=12" >}}
cats = cats + 2;
System.out.println("We now have " + cats + " cats on our farm.");
{{< / highlight >}}

Java also gives us shorthand to do this so that we don't have to write `cats`
twice.

{{< highlight java "linenos=table,linenostart=12" >}}
cats += 2;
System.out.println("We now have " + cats + " cats on our farm.");
{{< / highlight >}}

Subtraction (`-`), multiplication (`*`), division (`/`), the modulus operator
(`%`), and bitwise operators are all available.

We also have parenthesis available to group specific operations together, for
example:

{{< highlight java "linenos=table,linenostart=6" >}}
public static void main(String[] args) {
    int number = 5;
    int primary = number + 5 * 2;
    int other = (number + 5) * 2; // 20 instead of 15.
}
{{< / highlight >}}

#### Division

Division works a little differently than you'd expect when working with the
Integral types. When you are only allowed whole numbers, `5 / 2` or `11 / 7`
don't really fit in what you're allowed. Java solves this by cutting off the
remainder or fractional portion.

{{< highlight java "linenos=table,linenostart=6" >}}
int weird = 11 / 7;
System.out.println(weird); // Prints 1
{{< / highlight >}}

If you need the decimal portion of a remainder, `float`s and `double`s support
division as you'd expect.

#### Modulus

If you need the remainder of division, though, you need another operator. That's
where the modulus operator, `%` comes in. The modulus is *not quite* the
remainder, but in most cases it gives you the same thing.

{{< highlight java "linenos=table,linenostart=6" >}}
int weird = 11 % 7;
System.out.println(weird); // Prints 4
{{< / highlight >}}

This can also be used for some interesting things when we discuss loops.

#### Bitwise Operators

This section is a bit technical, so feel free to jump to
[here](#comparing-variables) if you're not interested in binary or working with
bits.

In Java, and every computer language, everything is stored as binary, `1`s and
`0`s. The integer 1 looks like this:

```
00000000 00000000 00000000 00000001 | 1
```

The integer 23 looks like this:

```
00000000 00000000 00000000 00010111 | 23
```

Each column represents a higher power of two. For example, 23 is `(1*2^0 + 1*2^1
+ 1*2^2 + 0*2^3 + 1*2^4 + 0*2^5 + ... + 0*2^31)`, or (1 + 2 + 4 + 0 + 16).[^2]
  This is how computers think about numbers, and being able to count by powers
  of two is a good skill to have when working with them.

[^2]: For more information about Binary, look [here](https://en.wikipedia.org/wiki/Binary_number#Representation).

Java provides some operators for working with numbers on this level. The most
basic kinds are the shifting operators, `<<` and `>>`. They move the bits in a
number left or right a certain number of times.

{{< highlight java "linenos=table,linenostart=6" >}}
int start = 23;
int next = 23 << 2;
System.out.println(next); // Prints 92
{{< / highlight >}}

For reference, the integer 92 in binary is:
```
00000000 00000000 00000000 01011100 | 92
```

Notice how the bits have been moved left 2 spaces. Interestingly, this has the
same effect as multiplying 23 by 4, or `23 * 2 ^ spaces`. Shifting right has the
same effect as dividing in the same way.

Next are the bitwise And (`&`), Or (`|`), and Exclusive Or (`^`) operators. Each of these
modifies bits relative to another set of bits. For example, `55 & 22` looks
like:

```
00000000 00000000 00000000 00110111 | 55
00000000 00000000 00000000 00011000 | 24 &
------------------------------------+-----
00000000 00000000 00000000 00010000 | 16
```

This is because `&` looks for places where there are 1s in both places. `|`
looks for places where there is a 1 in either place, like so:

```
00000000 00000000 00000000 00110111 | 55
00000000 00000000 00000000 00011000 | 24 |
------------------------------------+-----
00000000 00000000 00000000 00111111 | 63
```

And `^` looks for places where the places are different:

```
00000000 00000000 00000000 00110111 | 55
00000000 00000000 00000000 00011000 | 24 ^
------------------------------------+-----
00000000 00000000 00000000 00101111 | 47
```

{{< highlight java "linenos=table,linenostart=6" >}}
int xor = 55 ^ 2;
System.out.println(xor); // Prints 53, not 3025 
{{< / highlight >}}

It's good to be cautious, because many people come into the language thinking
that `^` means to the power of, when in fact it's an XOR, which leads to
confusion.

The last bitwise operator to be aware of is the NOT (`~`) operator. This simply
flips all ones to zeroes and zeroes to ones:

```
00000000 00000000 00000000 00110111 | 55 ~
------------------------------------+-----
11111111 11111111 11111111 11010000 |-56
```

In two's compliment representation[^3], as Java and many other languages use,
this is equal to the negative number minus one or positive number minus one.

[^3]: For more information on two's compliment, look [here](https://en.wikipedia.org/wiki/Two%27s_complement).

### Comparing Variables

Booleans are useful because they can be used to store if something is `true` or
`false`. While this seems relatively simple, they can be used for some complex
checks.

A relatively simple example is to store whether two variables are equal.

Back to our farm example, we can check if we have the same number of cats as we
do horses with the equality check operator, `==`:

{{< highlight java "linenos=table,linenostart=6" >}}
int chickens = 30;
int horses = 4;
int cows = 12;
int parrots = 7;
int cats = 22;
boolean sameCatsAndHorses = cats == horses;
System.out.println("Same number of cats and horses: " + sameCatsAndHorses);
{{< / highlight >}}

Some other important comparison operators are greater than (`>`), less than (`<`), greater than or equal to (`>=`), less than or equal to (`<=`), and not equal to (`!=`).

{{< highlight java "linenos=table,linenostart=6" >}}
boolean moreCats = cats > horses;
System.out.println("More cats than horses: " + moreCats);
{{< / highlight >}}

Something special about booleans is that since they are only `true` or `false`,
they can be switched back and forth with the boolean not operator (`!`).

{{< highlight java "linenos=table,linenostart=6" >}}
boolean moreCats = cats > horses;
System.out.println("More horses than cats: " + !moreCats);
{{< / highlight >}}

Booleans have some other useful operators, but we'll talk about those more when
we talk about `if` statements next time.

## Review

Today we went over the different types we have available in Java, and how each
of them are stored. We then went over how we can create and modify variables,
based on both literals and other variables. 

## Part 1 Assignment Answers

### 1. Try printing something other than `Hello World!`.

{{< highlight java "linenos=table" >}}
package me.hhenrichsen;

public class Java01 {
    public static void main(String[] args) {
        System.out.println("Something other than `Hello World!`");
    }
}
{{< / highlight >}}

### 2. Try printing your name.

{{< highlight java "linenos=table" >}}
package me.hhenrichsen;

public class Java01 {
    public static void main(String[] args) {
        System.out.println("Hunter");
    }
}
{{< / highlight >}}

### 3. What happens when you remove one of the keywords from the main method?

* If you remove `public`, it will compile but not run.
* If you remove `static`, it will compile but not run.
* If you remove `void`, it will not compile.
* If you remove `main`, it will not compile.
* If you replace `main`, it will compile but not run.
* If you remove `String[]`, it will not compile.
* If you remove `args`, it will not compile.
* If you replace `args`, it will compile and run.

### 4. What happens when you name a class differently from the file it's in?

It will fail to compile.

## Assignments

1. Create one variable of each type. What can each of them hold?
2. Try subtracting `1.3f` from `2.0f`. What happens?
3. Try creating some variables to represent numbers of animals. What can you
   tell us about the animal counts?

## Links

{{< lessonfooter java 2 >}}
