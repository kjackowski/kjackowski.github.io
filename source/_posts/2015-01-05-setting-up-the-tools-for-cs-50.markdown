---
layout: post
title: "Setting up the tools for CS 50"
date: 2015-01-05 13:45:11 +0100
comments: true
categories: linux
---

So CS 50 has officially begun. Time to get my computer ready for the work. 

The installation and use of the appliance is covered in great detail on the coursepages, so there is no need to describe it here. What I do different is that I plan to work mostly outside of the appliance, because my computer is barely able to run it and it is a pain in the backside to use it for longer periods (It's an old laptop, that wasn't powerful even when it was new.).
<!-- more -->
Since I am using Linux on my computer as the main operating system, setting it up for coding is not so big a task. Most of the packages are allready installed by me (the most important would be "build-essential", a metapackage, that brings compilers and stuff). Getting the functions from CS 50 to work is another thing.

First I followed the instructions on the [manual][2] for the CS 50 libraries. It was a lot of copy/pasting, but in the end the libraries in all four languages worked fine.

After that, I began to search for instructions for the other tools of the appliance, most important the check50 script. A nice [blogpost on medium][1] showed me where to look, but sadly the mentioned git-repository was deleted since then. I found a [copy of it on github][3] and tried to install it. Worked fine. But the most interesting part of it was the question: will it work with the current course?

For convenience I quickly made alias for it:
``` bash
alias check50="node /"path to my cs 50 folder"/cs50/check50/SOURCES/opt/check50/bin/check50.js"
```

After that, I tried the [example code from the coursesite][4]:
{% include_code [Hello World - The first try] hello-0.1.c %}

This compiled without visible errors, but when I made the compiling a little more verbose, I got this:

``` bash
$ CFLAGS="-Wall" make hello
cc -Wall    hello.c   -o hello
hello.c: In function ‘main’:
hello.c:6:1: warning: control reaches end of non-void function [-Wreturn-type]
}
^
```
One line more and the more verbose compiling also went on without errors:

{% include_code [Hello World - Without Warnings] hello.c %}

Time to use the code to test the check50 function with the new course:

``` bash
$ check50 2014.fall.pset1.hello hello.c
:) hello.c exists
:) hello.c compiles
:) prints "hello, world\n"
```

That went well. It seems like I am ready to dive into the coding problems and need only use the appliance for submitting the solutions. On the side, I have become somewhat comfortable with the functions, that [Octopress][5] provides for embedding code into blogposts.

[1]: https://medium.com/@ddiipp/take-harvards-cs50-without-cs50-appliance-8372acb91314
[2]: https://manual.cs50.net/library/
[3]: https://github.com/jthurner/check50
[4]: http://cdn.cs50.net/2015/x/psets/1/pset1/pset1.html#hello_c
[5]: http://octopress.org
