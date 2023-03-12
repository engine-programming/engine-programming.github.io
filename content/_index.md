+++
title =  "Learn Game Engine Programming"
date = 2022-08-25T21:30:04+08:00
draft = false
+++

This is a list of self-learning resources for game engine programming aimed at beginners. Some are free, some are paid. It is not exhaustive and does not cover everything you need to know to become a great engine programmer, but it will get you started and lead you part of the way. You are not required to follow this curriculum exactly, pick what you need. Some resources overlap in content, choose the ones that you like more, or consult several ones if you want things explained in multiple different ways.

# 1. Programming Basics

A good place to start is the [*Handmade Hero*](https://handmadehero.org/) video series by Casey Muratori. It has no prerequisites and shows how to make a game engine from scratch in C. However, the intro to C is rather brief and you may find it insufficient. In that case, complement it with other C and C++ resources listed in the next section.

Otherwise, there is an abundance of resources for learning the basics of programming in ways not explicitly related to engines. They are not listed here. The rest of this guide assumes that you already know programming in at least one language.

As part of your basic training, it is also useful to learn the fundamentals of algorithms and data structures. A book that uses C to teach them is [*The Algorithm Design Manual*](https://www.algorist.com/) by Steven Skiena.

A website that offers fun exercises to practice algorithms and data structures is [*Advent of Code*](https://adventofcode.com/). New challenges are added every year in December.

# 2. Programming Languages

Engines are mostly written in C and C++ because these languages map somewhat directly to how the CPU works, which allows to achieve high performance.

[*Modern C*](https://gustedt.gitlabpages.inria.fr/modern-c/) by Jens Gustedt introduces the C language. It is not aimed at complete beginners because it teaches the specifics of the language, as opposed to general programming concepts.

C++ is built on the foundations laid out by C. It is a huge language with many parts and features. Engine programmers usually like to use some parts, but less so other parts (more about that in the next section). Regardless of whether you like some features or not, you are likely to encounter most of them at some point in your career, so it is useful to learn about them once even if you do not use them frequently.

*C++ Primer* by Stanley Lippman, Josée Lajoie, and Barbara E. Moo is an introductory book that is accessible to beginners. You can also start directly there without first learning C.

When you need to quickly look up some details, an online reference for C and C++ is [cppreference.com](https://en.cppreference.com/). If you need a reference written in a more informal style and that is easier to read, [*The C++ Programming Language*](https://www.stroustrup.com/4th.html) by Bjarne Stroustrup is useful.

# 3. Programming Best Practices

[*The Rules of Programming: How to Write Better Code*](https://www.oreilly.com/library/view/the-rules-of/9781098133108/) by Chris Zimmerman explains the programming practices used at the video game studio Sucker Punch Productions where they make their own engine. Many examples are drawn from their games.

Engine programmers avoid using some parts of C++. It can depend on personal preference, but sometimes also for good reasons. Here are common examples with links to typical justifications:
* Splitting code into many small functions: [John Carmack on Inlined Code](http://number-none.com/blow/john_carmack_on_inlined_code.html).
* Object-oriented features such as virtual functions: [*"Clean" Code, Horrible Performance*](https://www.computerenhance.com/p/clean-code-horrible-performance) by Casey Muratori.
* The STL: [Twitter thread](https://twitter.com/m_ninepoints/status/1497768472184430600) by Jeremy Ong. Many engine programmers end up developing their own replacement of the STL, such as the [Electronics Arts Standard Template Library](https://github.com/electronicarts/EASTL) whose documentation contains justifications.
* Exceptions: [Hacker News comment](https://news.ycombinator.com/item?id=28164247) by Walter Bright.

# 4. Computer Architecture and Performance

## General

The [*Performance-Aware Programming* Series](https://www.computerenhance.com/p/welcome-to-the-performance-aware) by Casey Muratori teaches the basics.

The book [*Computer Systems: A Programmer's Perspective*](http://csapp.cs.cmu.edu/) by Randal E. Bryant and David R. O'Hallaron also covers the fundamentals. Additionally, it introduces systems programming on Linux. Most game programming is done on Windows, but the concepts covered in the book are fundamental enough to carry over. It requires Linux for doing some of the labs.

A reference for the performance characteristics of x86 instructions is [uops.info](https://uops.info/).

A reference for intrinsics is the [Intel Intrinsics Guide](https://www.intel.com/content/www/us/en/docs/intrinsics-guide/index.html).

A tool to see the floating point representation of a number is [Float Exposed](https://float.exposed/).

## Advanced Computer Architecture

Knowing the basics well is enough as a beginning generalist engine programmer. Though if you want to specialize in optimization, *Computer Architecture: A Quantitative Approach* by John L. Hennessy and David A. Patterson gives a lot more details about the way hardware works.

## Assembly

It is important to know how to read assembly, but not necessarily to write it yourself. One of the main uses is to verify that the compiler did what you expect with your code, for example in terms of optimization.

[Compiler Explorer](https://godbolt.org/) is a tool that lets you see the assembly that various compilers produce from your code snippets. You can learn a lot just by playing with it.

The incomplete [*Applied Reverse Engineering*](https://revers.engineering/applied-reverse-engineering-series/) series by Daax Rynd currently covers the basics.

The book [*Reverse Engineering for Beginners*](https://beginners.re/) by Dennis Yurichev is more complete.

For an online reference, you can use [www.felixcloutier.com/x86/](https://www.felixcloutier.com/x86/).

## Data-Oriented Design

A programming approach often adopted in engine programming is known as data-oriented design. It aims at increasing performance by organizing programs to take advantage of the way that modern CPUs work, in particular with respect to caching. This approach is introduced in:
* [*Efficiency with Algorithms, Performance with Data Structures*](https://www.youtube.com/watch?v=fHNmRkzxHWs) by Chandler Carruth.
* [*Optimizable Code*](https://deplinenoise.wordpress.com/2013/12/28/optimizable-code/) by Andreas Fredriksson.
* [*Data-Oriented Design and C++*](https://www.youtube.com/watch?v=rX0ItVEVjHc) by Mike Acton.
* [*Practical Optimizations*](https://www.youtube.com/watch?v=NAVbI1HIzCE) by Jason Booth.

# 5. Engine Programming

## General

Finally, you have learned the fundamentals and it is now time to learn about game engines. You do not need to finish learning all the fundamentals before starting this.

[*Game Engine Architecture*](https://www.gameenginebook.com/) by Jason Gregory gives a broad overview of how game engines are organized. It will make you familiar with the different parts of a typical engine.

The [*Foundations of Game Engine Development*](https://foundationsofgameenginedev.com/) series by Eric Lengyel is not finished yet, but two books are currently available. It covers fundamentals, not the most advanced topics, but it does so in enough detail to enable you to make proper implementations. If you are learning the math of the first book for the first time, it may be too short of an introduction. In that case, refer to the math appendix section of this guide for more complete resources.

Mike Acton gives his advice to new engine programmers in his talk [*Solving the Right Problems for Engine Programmers*](https://www.youtube.com/watch?v=4B00hV3wmMY).

## Rendering

Rendering is one of the most important parts of an engine. The roles are often split between generalist engine programmer and rendering programmer. However, even as a generalist, you need to know the basics.

Jeremy Ong gives advice on [how to learn graphics programming](https://twitter.com/m_ninepoints/status/1215429886715629569) on Twitter.

Cem Yuksel's video lectures are general introductions: [*Introduction to Computer Graphics*](https://www.youtube.com/playlist?list=PLplnkTzzqsZTfYh4UbhLGpI5kGd5oW_Hh) and [*Interactive Computer Graphics*](https://www.youtube.com/playlist?list=PLplnkTzzqsZS3R5DjmCQsqupu43oS9CFN).

For a text, [*Learning Modern 3D Graphics Programming*](https://paroj.github.io/gltut/) introduces graphics using OpenGL.

[*A trip through the Graphics Pipeline*](https://fgiesen.wordpress.com/2011/07/09/a-trip-through-the-graphics-pipeline-2011-index/) by Fabian Giesen gives an overview of the steps taking place in the GPU when rendering.

A reference that covers a lot of topics is [*Real-Time Rendering*](https://www.realtimerendering.com/) by Tomas Akenine-Möller, Eric Haines, Naty Hoffman, Angelo Pesce, Michał Iwanicki, and Sébastien Hillaire. This itself contains many references to resources for the various presented techniques.

The [*Ray Tracing in One Weekend*](https://raytracing.github.io/) book series by Peter Shirley is a short introduction to ray tracing. This is not on GPU, but the principles are useful for real-time rendering as well.

A much more complete path tracer is explored in [*Physically Based Rendering: From Theory to Implementation*](https://www.pbrt.org/) by Matt Pharr, Wenzel Jakob, and Greg Humphreys. It covers the theory of physically based rendering and also demonstrates an implementation.

To use the GPU, you need to go through a graphics API. Direct3D 11 is easy to start with. Direct3D 12 and Vulkan are more complex and could hinder your learning of graphics itself. Below are resources for these APIs.

Direct3D 11:
* [The official documentation](https://learn.microsoft.com/en-us/windows/win32/direct3d11/atoc-dx-graphics-direct3d-11).
* d7samurai's samples: [part 1](https://gist.github.com/d7samurai/261c69490cce0620d0bfc93003cd1052), [2](https://gist.github.com/d7samurai/aee35fd5d132c51e8b0a78699cbaa1e4) and [3](https://gist.github.com/d7samurai/abab8a580d0298cb2f34a44eec41d39d).
* [Mārtiņš Možeiko's sample](https://gist.github.com/mmozeiko/5e727f845db182d468a34d524508ad5f).

Direct3D 12:
* [The official documentation](https://learn.microsoft.com/en-us/windows/win32/direct3d12/direct3d-12-graphics).
* [Microsoft's samples](https://github.com/microsoft/DirectX-Graphics-Samples).
* [*A Gentle Introduction to D3D12*](https://alextardif.com/DX12Tutorial.html) by Alex Tardif.

Vulkan:
* [*The specification*](https://registry.khronos.org/vulkan/specs/1.1/html/vkspec.html).
* [*How to Learn Vulkan*](https://www.jeremyong.com/c++/vulkan/graphics/rendering/2018/03/26/how-to-learn-vulkan/) by Jeremy Ong.
* [*Vulkan in 30 minutes*](https://renderdoc.org/vulkan-in-30-minutes.html) by baldurk.
* [*API without Secrets: Introduction to Vulkan*](https://www.intel.com/content/www/us/en/developer/articles/training/api-without-secrets-introduction-to-vulkan-preface.html) by Pawel Lapinski.
* [*Vulkan Tutorial*](https://vulkan-tutorial.com/) by Alexander Overvoorde.
* [Vulkan C++ examples and demos](https://github.com/SaschaWillems/Vulkan) by Sascha Willems.
* *Vulkan Synchronization Primer*, [part 1](https://www.jeremyong.com/vulkan/graphics/rendering/2018/11/22/vulkan-synchronization-primer/) and [2](https://www.jeremyong.com/vulkan/graphics/rendering/2018/11/23/vulkan-synchonization-primer-part-ii/) by Jeremy Ong.

## Physics

[*Game Physics*](https://gafferongames.com/post/integration_basics/) by Glenn Fiedler is a series of easy articles introducing physics for games.

[*Real-Time Collision Detection*](https://realtimecollisiondetection.net/) by Christer Ericson covers the data structures and algorithms used for collision detection.

## Networking

[*What is Rollback Netcode?*](https://bymuno.com/post/rollback) by Muno illustrates rollback netcode using gifs. It gives an intuition for some of the problems that networking can face in games.

Glenn Fiedler wrote many articles about networking in different series.
* [*Networking for Game Programmers*](https://gafferongames.com/categories/game-networking/)
* [*Networked Physics*](https://gafferongames.com/categories/networked-physics/)
* [*Building a Game Network Protocol*](https://gafferongames.com/categories/building-a-game-network-protocol/)

# FAQ
