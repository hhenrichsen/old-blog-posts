---
title: "Java Tutorial Part 1: Introduction"
date: 2019-08-04T22:42:35-06:00
draft: false
toc: true
images:
author: Hunter Henrichsen
tags:
  - java
  - java-tutorial
---

## Introduction

I'm not going to lie to you -- learning programming is a difficult road. Though
many chose to start it, few decide to complete it. Some start early on, and
others take a winding path to find that this is what they want to be doing.
Either way, everyone needs to start somewhere. I'm hoping that here might be a
good place for you to do it. 

By no means am I the best teacher, but I have some ideas about how I want to
approach this that are a little different than others. First, instead of just
showing you what Java has available to you, I want to provide projects at the
end of each lesson that stretch your thinking and ask you to use what you've
learned in interesting ways. I also want to encourage you to not just cut and
paste what I write as code, but instead write your own. To this end, in later
lessons I'll illustrate concepts with smaller focused blocks of code and leave
it to you to fill in what is needed to make it go. If you're not okay with
either of these things, you may be better off looking elsewhere.

To combat this slightly, I make myself available on
[Discord](https://discord.hhenrichsen.me/), [GitHub](https://github.com/), and
[Twitter](https://twitter.com/hhenrichsen_) for questions on programming. Run
into an error that you don't know how to fix?  Shoot me a message. I'll do my
best to answer what I can.

If you're still around, then maybe we should get started. 

## Getting Started

### Installing the JDK

The first step of getting started with Java is to install Java. Who would have
thought? Java 12 is the latest General Availability version of Java available at
the time of writing. The JDK, or Java Development Kit, can be downloaded
[here](https://adoptopenjdk.net/index.html).
It contains everything you need to compile and run Java code. Please note that
recently, Oracle has changed the licenses on Java and the ways that it can be
used[^1], which is why I recommend using OpenJDK which remains free. I will be
using Java 8 for this tutorial, but other versions should work just as well.

[^1]: Read more about this [here](https://www.oracle.com/technetwork/java/javase/overview/oracle-jdk-faqs.html), [here](https://adoptopenjdk.net/about.html) and [here](https://medium.com/@javachampions/java-is-still-free-2-0-0-6b9aa8d6d244).

I can't provide instructions on how to install the JDK for every operating
system available. For most, it's as simple as downloading and running a file,
but it depends on which distribution you use. 

To check if the JDK installed correctly, open up a terminal (On Windows, press
the Windows Key and type `cmd`) and then type `java -version`.

If you need help, feel free to jump into Discord or contact me some other way.

### Choosing an Editor

The next important part of getting started with Java is choosing an editor. For
this tutorial, all screenshots will be from [IntelliJ IDEA: Community
Edition](https://www.jetbrains.com/idea/download/#section=windows). This is the
editor that I use when I'm not using vim, and is built for Java. Some people
will recommend [Eclipse](https://www.eclipse.org/). Both are free, and both can
do what we're going to do in this tutorial.

Either way, the next step is to download and install your editor of choice.
Since mine is IntelliJ, I'm going to download and install that one. If you would
rather use Eclipse or something else, I'll leave you to set that up on your own.
When you're done with that, go ahead and skip down [here](#storing-code).

### Setting Up IntelliJ

The first window I get after I've installed IntelliJ is one asking me about
importing settings. I'm going to choose not to import anything.

Next I get this window:

![Config 1](/img/java-01/Config1.png)

For this one, I'll pick Darcula because I like dark color schemes better. If you
prefer the light theme, go for it. Just like this site, the editor has support
for both.

For the sake of simplicity I'm just going to chose **Skip Remaining and Set
Defaults** for the rest of the settings. If you want to configure different
settings and plugins, feel free to go through those.

Then, I get a window like this:

![Getting Started](/img/java-01/GettingStarted.png)

I'm going to create a new project, because I don't have anything else to open at
this point. 

When I do that, I get this dialog:

![New Project](/img/java-01/NewProject.png)

I'm just going to click **Next** because this isn't based off of any libraries,
build managers, or other frameworks, and **Next** again because I'm not using a
template for this project. That gives me this window:

![New Project Name](/img/java-01/NewProjectName.png)

I'm going to name this one `LearnJava` because that's what we're going to do
with this one. Feel free to name it as you like. Once you have a name, go ahead
and click **Next** again.

![New Project Open](/img/java-01/NewProjectOpen.png)

Once we click that, IntelliJ will open in full. Mine has a progress bar in the
bottom left as it scans for files that exist in this project, and will let you
know if there are any issues.

### Storing Code

Now our goal is to send a message to whoever runs our program. We'll start off
with something simple, like "Hello World!"

To do that, we need to have some containers for our code. In Java, these are
called **Packages**. Normally these are named in the style of a reversed domain,
so mine would be `me.hhenrichsen`. If you don't own a domain or want to use
this, you can name these whatever you want. They're just a way to organize code
into smaller groups.

I'm going to put my package in the `src` folder, which IntelliJ generates for me
when I make a new project. Feel free to make this folder if you don't have one.

In IntelliJ, creating a package looks like this:

![Creating a Package](/img/java-01/NewPackage.png)

Now that we have a place to put our code, let's create a file to code in. In
Java, these are files that end in `.java` for source code. Since Java enforces
strict Object Oriented Programming and naming, these must be named the same as
the class as is inside them. I'm going to create one for this chapter named
`Java01.java`. 

Creating a class in IntelliJ looks like this:

![Creating a Class](/img/java-01/NewClass.png)

Every class starts off with some code thanks to IntelliJ, and many other editors
will start you off with some similar code. Mine looks like this:

![Open Editor](/img/java-01/OpenEditor.png)

`Java01.java`
{{< highlight java "linenos=table,hl_lines=5,linenostart=1" >}}
package me.hhenrichsen;

public class Java01 {
}
{{< / highlight >}}

### The Main Method

Now we're going to add a little more code to this file so that it will do
something when we run it.

The first bit we're going to add is the main method. This is a very special
method or function in Java that determines what happens when the program
starts. It looks like this:

`Java01.java`
{{< highlight java "linenos=table,hl_lines=5,linenostart=1" >}}
package me.hhenrichsen;

public class Java01 {
    public static void main(String[] args) {
        
    }
}
{{< / highlight >}}

There are a few special words here called Keywords. Most editors will light
these up in different colors. Keywords have special meanings and do different
things depending on where they are.

For now we'll define the ones we have as follows:

* `public` - Anyone has access to it, just like public bathrooms.
* `static` - This is sticky to `Java01`, and doesn't change.
* `void` - This method or function doesn't return anything, or give anything
  back.

`main` is the name of the method. This name is how we can find it, and is how
Java finds this method.

Next in the parenthesis we can find parameters, or things that are given to this
method when we use it. `String[]` means a list of text, and `args` is another
name that we use to access something. In this case, Java gives us anything that
comes along with the program when it's called, or the **Command Line Arguments**.

Right now we don't have our main method set up to do anything. How about we fix
that?

### Hello World!

`Java01.java`
{{< highlight java "linenos=table,hl_lines=5,linenostart=1" >}}
package me.hhenrichsen;

public class Java01 {
    public static void main(String[] args) {
        System.out.println("Hello World!");        
    }
}
{{< / highlight >}}

Now we're calling a method! This one is called `System.out.println()`, and its
job is to print a message to the console. We tell it which message to send in
the parenthesis, in this case, `Hello World!`. Notice how we need to add quotes
around this message. That's because we're making a `String`, but we'll talk
about that later. 

Another important thing to notice is that every method call or assignment in
Java ends with a semicolon (`;`). This tells Java "Hey, this is the end of
whatever command this is. On to the next one!"

If you're using IntelliJ, you might notice two green play buttons have appeared
in the left margin. Go ahead and click one of them, and then select **Run
Java01.main()**. It'll compile the code for you, and at the bottom the output
will pop up. Mine looks like this:

![Hello World!](/img/java-01/HelloWorld.png)

If you look at the bottom, you can see that `Hello World!` gets printed.
Congratulations! You're on your first step to being able to talk to computers!

## Assignments

Here is where I'll give you a few things to try before you attempt the next
lesson. Doing these and thinking about them before looking at the solutions in
the next lesson is important to learning Java.

1. Try printing something other than `Hello World!`
2. Try printing your name.
3. What happens when you remove one of the keywords from the main method?
4. What happens when you name a class differently from the file it's in?

## Links

{{< lessonfooter java 1 >}}
