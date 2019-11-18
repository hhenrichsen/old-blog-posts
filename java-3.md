---
title: "Java Tutorial Part 3: Checking Conditions"
date: 2019-08-11T17:46:40-06:00
draft: false
toc: true
tags:
  - java
  - java-tutorial
---
## Overview

In our last lesson, we looked at how we can store different types of data. In
one of those, we looked at how we can store something called a `boolean` that
can store either a `true` or `false`. Today we're going to look at how we can
write code that only gets run that condition is true.

## Boolean Review

*Note: If you remember what was covered in the last lesson, or are familiar with
comparison operators already, feel free to skip [here](#the-if-statement).*

If you recall, `boolean`s are the smallest primitive type, and work similar to a
light switch: they can either be on, or off. Booleans can start off as a value,
but we can also see if other things are true or false, using comparison
operators. 

The most basic of these comparison operators is the equality operator, `==`. It
is true if both sides are the same thing, and false if either of the sides are
different.

For example:

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    boolean same = (a == b); // Parenthesis added for clarity.
    System.out.println("Are A and B the same? " + same);
}
{{< / highlight >}}

Prints `Are A and B the same? false`.

There is a collection of operators for booleans that can be found
[here](/posts/java-02/#comparing-variables).

I think the above code would be cooler if we could send different messages based
on if A and B were the same or not. Lucky for us, Java has us covered.

## The If Statement

Enter: the `if` statement. Making decisions based on conditions is one of the
most important things in programming, and can be seen based on every programming
language's ability to check conditions in some shape or form.

In Java, an if statement takes the following form:

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    boolean same = (a == b);
    if(same) {
        System.out.println("A and B are the same.");
    }
}
{{< / highlight >}}

The first thing you'll notice is that we have a new set of curly braces, `{ }`.
That's called a new **block of code**, and similar to what we have after the
`main` method, it's a way of grouping things together.

If you run this program, you'll notice that nothing gets printed. That's because
`same` is `false`, and if statements only get executed if whatever's in the
parenthesis is `true`.

Something neat that you can do to make this print is to **Negate** the boolean.
We use the negation operator, `!`, to do this:

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    boolean same = (a == b);
    if(!same) {
        System.out.println("A and B are not the same.");
    }
}
{{< / highlight >}}

Running this, you'll notice that `A and B are not the same.` gets printed. 

*Quiz: How would you write this using a comparison operator instead of a
negation?*

## The Else Statement

Looking at the first time we looked at `if` statements above, it's a little
confusing when you run the code. Nothing gets printed! We could write something
with two if statements, like this:

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    boolean same = (a == b);
    if (same) {
        System.out.println("A and B are the same!");
    }
    if (!same) {
        System.out.println("A and B are not the same.");
    }
}
{{< / highlight >}}

That seems like a lot of repetition, though, and an important thing to think
about when writing code is how much we're repeating things. If we copy and paste
code a bunch of times, and then decide that we want to change it, we have to go
back and change every single time we pasted it. 

Java likes to help us out in this regard. Enter: the `else` statement. `Else`
statements can be tacked on to the end of `if` statements. The above code can be
changed to use one of these.

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    boolean same = (a == b);
    if (same) {
        System.out.println("A and B are the same!");
    }
    else {
        System.out.println("A and B are not the same.");
    }
}
{{< / highlight >}}

This looks a lot cleaner. Else statements are evaluated only if the `if`
statement does not execute its block of code.

### Aside: Creating Booleans In-Place

Some attentive readers may have already predicted this, but creating a boolean
every time we want to do an if statement seems like a lot of work. As I've said
a couple times at this point, any place a literal can be used, a variable can be
used and vice versa. Let's apply this to `if` statements!

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    if (a == b) {
        System.out.println("A and B are the same!");
    }
    else {
        System.out.println("A and B are not the same!");
    }
}
{{< / highlight >}}

Notice how the `boolean same` is gone, and what it was set to has been moved
into the if statement itself. If you try to run it, you'll notice that it
behaves just like the above!

This is the more common way you'll see `if` statements used, and already it
looks a lot cleaner. 

## The Else If Statement

With the above, we'd have trouble if we wanted to print messages based on if the
numbers are less than each other, equal to each other, and greater than each
other. We can accomplish this with multiple if statements, but we can also write
clearer code by using a different way.

This is accomplished by simply attaching an `if` statement on to the end of an
`else` statement, and is known as an `else if` statement.

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    if (a < b) {
        System.out.prinlnt("A is less than B.");
    }
    else if (a == b) {
        System.out.println("A is equal to B.");
    }
    else { // a > b
        System.out.println("A is greater than B.");
    }
}
{{< / highlight >}}

The advantage to these, besides being clearer, is that the minimum amount of
code is executed. If `a` was less than `b`, Java would run the code in the first
block and then skip past the rest of them. 

## Combining Boolean Conditions

You may have guessed that if you wanted to check two things before running a
block of code, that you can put two `if` statements inside each other, or if you
wanted one of two things to be true, you could rewrite the code twice. This
doesn't quite go with what programmers like to do. We like to write things once,
and use them over and over. 

Instead, we have more operators we can use on booleans. Just like if we wanted
to check if something is equal by using two equals signs, we can do something
similar with and signs.

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    if (a > 5 && b < 20) {
        System.out.prinlnt("A is greater than 5, and B is less than 20.");
    }
}
{{< / highlight >}}

Similarly, if we only want to require one of these, we can use the pipe symbol
(`|`, normally left of the brackets), which is used to represent or.

{{< highlight java "linenos=table,linenostart=3" >}}
public static void main(String[] args) {
    int a = 15;
    int b = 12;
    if (a > 5 || b > 20) {
        System.out.prinlnt("A is greater than 5, or B is less than 20.");
    }
}
{{< / highlight >}}

These are called boolean operators, and they work to combine more than one
boolean into one. These can be used when booleans are created if a
condition needs to be stored for later.

## Part 2 Assignment Answers

### 1. Create one variable of each type. What can each of them hold?

{{< highlight java "linenos=table,linenostart=5" >}}
boolean yes = true; // Holds true or false.
char letterC = 'c'; // Holds one letter.
short smallWholeNumber = 5; // Holds a small whole number.
int wholeNumber = 1; // Holds a whole number.
long bigWholeNumber = 2L; // Holds a large whole number.
float decimal = 0.3f; // Holds a decimal.
dobule moreAccurateDecimal = 12.123d; // Holds a decimal. More precise than a float.
{{< / highlight >}}

### 2. Try subtracting 1.3f from 2.0f. What happens?

{{< highlight java "linenos=table,linenostart=5">}}
System.out.println(2.0f - 1.3f);
{{< / highlight >}}

Notice how this outputs something like `0.700000000005`. This is because a float
can't accurately estimate 0.7.

### 3. Try creating some variables to represent numbers of animals. What can you tell us about the animal counts?

{{< highlight java "linenos=table,linenostart=5" >}}
int chickens = 30;
int horses = 4;
int cows = 12;
int parrots = 7;
int cats = 22;
int total = chickens + horses + cows + parrots + cats;
double fourLegs = (horses + cows + cats) / total; 
System.out.println(fourLegs * 100 + "% of the animals have 4 legs.");
{{< / highlight >}}

This is just one example of the types of things you can do with variables.

## Assignment

1. Which block of code in an if-else statement would be executed if the `if`
   contained `true`?
2. Try writing an `if` statement with a few different variables using boolean
   operators that only works if a few conditions are met.

## Links
{{< lessonfooter java 3 >}}
