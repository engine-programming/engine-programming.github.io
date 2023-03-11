+++
title =  "Learn Game Engine Programming"
date = 2022-08-25T21:30:04+08:00
draft = false
+++

This is a list of self-learning resources for game engine programming aimed at beginners. Some are free, some are paid. It is not exhaustive and does not cover everything you need to know to become a great engine programmer, but it will get you started and lead you part of the way. You are not required to follow this curriculum exactly, pick what you need. Some resources overlap in content, choose the ones that you like more, or consult several ones if you want things explained in multiple different ways.

# 1. Programming Basics

A good place to start is the [Handmade Hero](https://handmadehero.org/) video series by Casey Muratori. It has no prerequisites and shows how to make a game engine from scratch in C. However, the intro to C is rather brief and you may find it insufficient. In that case, complement it with other C resources listed below.

Otherwise, there is an abundance of resources for learning the basics of programming in ways not explicitly related to engines. They are not listed here. The rest of this guide assumes that you already know programming in at least one language.

# 2. Programming Languages

Engines are mostly programmed in C and C++ because these languages map somewhat directly to how the CPU works, which allows to achieve high performance.

[Modern C](https://gustedt.gitlabpages.inria.fr/modern-c/) by Jens Gustedt introduces the language. It is not aimed at complete beginners, it teaches the specifics of the language, as opposed to general programming concepts.

C++ is built on the foundations laid out by C. It is a huge language with many parts and features. Engine programmers usually like to use some parts, but less so other parts (more about that in the next section). Regardless of whether you like them or not, you are likely to encounter most features at some point in your career, so it is useful to learn about them once even if you do not use them.

C++ Primer by Stanley Lippman, Josée Lajoie, and Barbara E. Moo is an introductory book that is accessible to beginners. You can also start directly there without first learning C. The first part of the book covers the C subset of C++.

When you need to quickly look up some details, the best C and C++ reference online is [cppreference.com](https://en.cppreference.com/). If you need something that is written in a more informal style and that is easier to consume, [The C++ Programming Language](https://www.stroustrup.com/4th.html) by Bjarne Stroustrup is useful.

# 3. Programming Best Practices

[The Rules of Programming: How to Write Better Code](https://www.oreilly.com/library/view/the-rules-of/9781098133108/) by Chris Zimmerman explains the programming practices used at the video game studio Sucker Punch Productions where they develop their own engine. Many of the examples are drawn from the code of their games. The book is pragmatic, it does not stoop to dogmatism and it does not present its rules as absolute.

Many engine programmers avoid using some parts of C++. It can depend on personal preference, but sometimes also for good reasons. Here are common examples with links to typical justifications:
* Splitting code into many small functions: [John Carmack on Inlined Code](http://number-none.com/blow/john_carmack_on_inlined_code.html).
* Object-oriented features such as virtual functions: ["Clean" Code, Horrible Performance](https://www.computerenhance.com/p/clean-code-horrible-performance) by Casey Muratori.
* The STL: [Twitter thread](https://twitter.com/m_ninepoints/status/1497768472184430600) by Jeremy Ong. Many engine programmers end up developping their own replacement of the STL, such as the [Electronics Arts Standard Template Library](https://github.com/electronicarts/EASTL) whose documentation contains many justifications for doing so.
* Exceptions: [Hacker News comment](https://news.ycombinator.com/item?id=28164247) by Walter Bright.
* And so on...

# FAQ
