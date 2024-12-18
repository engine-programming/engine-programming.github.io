+++
title =  "Learn Game Engine Programming"
date = 2022-08-25T21:30:04+08:00
draft = false
+++

This is a list of self-learning resources for game engine programming. It is not exhaustive, there are many more things to learn, but it will get you started. The content is organized sequentially, but the order is not strict, feel free to jump around.

# 1. Programming Basics

Engines are mostly written in C++ because it maps somewhat directly to how the CPU works, which allows to achieve high performance.

* [*Handmade Hero*](https://handmadehero.org/) by Casey Muratori shows how to make an engine in C, which is a subset of C++. It has no prerequisites, but the intro to C might feel insufficient if you do not already have some programming experience.

* [*The Definitive C++ Book Guide and List*](https://stackoverflow.com/questions/388242/the-definitive-c-book-guide-and-list) on Stack Overflow recommends several books, such as *C++ Primer* by Stanley Lippman, Josée Lajoie, and Barbara E. Moo.

* Online reference: [cppreference.com](https://en.cppreference.com/).

# 2. Programming Best Practices

* [*The Rules of Programming: How to Write Better Code*](https://www.therulesofprogramming.com/) by Chris Zimmerman explains the programming practices used at Sucker Punch where they make their own engine. It is one of the most beneficial books you can read as a beginner. Although the examples are in C++, the focus is not on the language itself but on general programming practices.

C++ is a huge language with many parts and features that can be used (and misused) in many different ways. Handmade Hero teaches low-level C-style code, whereas general C++ books teach more abstract paradigms such as object-oriented programming. Some programmers have very strong opinions about the right way to do things. Engine programmers tend toward low-level code. However, you will likely encounter all kinds of code through your career.

* *Effective C++* and *Effective Modern C++* by Scott Meyers cover standard C++ idioms and practices that are widespread in objet-oriented codebases. It is useful to think critically about the strengths and weaknesses of such practices.

Further resources:

* [John Carmack on Inlined Code](http://number-none.com/blow/john_carmack_on_inlined_code.html).
* [John Carmack on Functional Programming in C++](http://www.sevangelatos.com/john-carmack-on/).
* [*"Clean" Code, Horrible Performance*](https://www.computerenhance.com/p/clean-code-horrible-performance) by Casey Muratori on object-oriented features such as virtual functions.
* Many engines use their own replacement of the STL, such as the [Electronics Arts Standard Template Library](https://github.com/electronicarts/EASTL) whose documentation contains [justifications](https://github.com/electronicarts/EASTL/blob/master/doc/FAQ.md#info6-why-is-there-eastl-when-there-is-the-stl).
* [Walter Bright on exceptions](https://news.ycombinator.com/item?id=28164247).
* [Why Should I Care What Color the Bikeshed Is?](https://bikeshed.com/) by Poul-Henning.

# 3. Algorithms and Data Structures

Algorithms and data structures are fundamental to solving problems with code. They are used everywhere in engines. You need to know their characteristics.

* [*The Algorithm Design Manual*](https://www.algorist.com/) by Steven Skiena uses C to teach them.

Further resources:

* *Hacker's Delight* by Henry S. Warren, Jr. is about bit manipulation tricks.
* [*Advent of Code*](https://adventofcode.com/) is a website with fun exercises to practice.

# 4. Computer Architecture and Performance

Engine programming requires a good understanding of how computers work in order to achieve the high performance required for real-time interactive games.

These resources cover the basics broadly:

* The [*Performance-Aware Programming* Series](https://www.computerenhance.com/p/welcome-to-the-performance-aware) by Casey Muratori teaches the essentials. It is currently in production, with a weekly release schedule.
* [*Computer Systems: A Programmer's Perspective*](http://csapp.cs.cmu.edu/) by Randal E. Bryant and David R. O'Hallaron. If Performance Aware doesn't yet cover a topic, you could look here to get started.

The other resources listed below dive deeper into specific topics.

Assembly, which you do not necessarily need to know how to write, but at least to read in order to verify that the compiler did what you expect with your code:

* [*Applied Reverse Engineering*](https://revers.engineering/applied-reverse-engineering-series/) by Daax Rynd, although it is still unfinished.
* [*Reverse Engineering for Beginners*](https://beginners.re/) by Dennis Yurichev, a more complete book.

Data-oriented design, a programming approach that takes advantage of the way that modern CPUs work, in particular with respect to caching:

* [*Efficiency with Algorithms, Performance with Data Structures*](https://www.youtube.com/watch?v=fHNmRkzxHWs) by Chandler Carruth.
* [*Optimizable Code*](https://deplinenoise.wordpress.com/2013/12/28/optimizable-code/) by Andreas Fredriksson.
* [*Data-Oriented Design and C++*](https://www.youtube.com/watch?v=rX0ItVEVjHc) by Mike Acton.

Parallel programming, which becomes increasingly important as CPUs get more cores:

* [*Is Parallel Programming Hard, And, If So, What Can You Do About It?*](https://mirrors.edge.kernel.org/pub/linux/kernel/people/paulmck/perfbook/perfbook.html) by Paul E. McKenney.

Advanced resources if you want to further specialize in optimization:

* *Computer Architecture: A Quantitative Approach* by John L. Hennessy and David A. Patterson gives a lot more details about the way hardware works.
* Agner Fog wrote several advanced [*optimization manuals*](https://www.agner.org/optimize/#manuals).

Misc useful links:

* x86 instructions: [www.felixcloutier.com/x86/](https://www.felixcloutier.com/x86/).
* Performance characteristics of x86 instructions: [uops.info](https://uops.info/).
* [Compiler Explorer](https://godbolt.org/) is a tool that lets you see the assembly that various compilers produce from your code snippets.
* Online reference for intrinsics: [Intel Intrinsics Guide](https://www.intel.com/content/www/us/en/docs/intrinsics-guide/index.html).
* Tool to see the floating point representation of a number: [Float Exposed](https://float.exposed/).

# 5. Math

Some parts of an engine use math, such as rendering and physics. The most important fields are trigonometry, calculus, and linear algebra. Only resources at a level above high-school are listed here.

While it is useful to learn these topics eventually, some find it better to learn them when the necessity becomes manifest in practice. If that is your case, come back here later as needed.

Calculus:
* [*Calculus GREEN*](https://www.youtube.com/playlist?list=PL8erL0pXF3JaFSMdokheNMvTa96jdc4GU) by Robert Ghrist. The course is not complete yet.

Introductory linear algebra:
* [*Calculus BLUE Vol 1 : Vectors & Matrices*](https://www.youtube.com/playlist?list=PL8erL0pXF3JYm7VaTdKDaWc8Q3FuP8Sa7) by Robert Ghrist.
* [*Essence of Linear Algebra*](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) by 3Blue1Brown.
* [*Linear Algebra*](https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/) by Gilbert Strang.

Rigorous linear algebra:
* [*Linear Algebra Done Right*](https://linear.axler.net/) by Sheldon Axler.
* [*Linear Algebra Done Wrong*](https://www.math.brown.edu/streil/papers/LADW/LADW.html) by Sergei Treil.

# 6. Engine Programming

With the fundamental knowledge learned so far, you know enough to finally consider engines.

## General

* [*Game Engine Architecture*](https://www.gameenginebook.com/) by Jason Gregory gives a broad overview of how engines are organized. It will make you familiar with the different parts of a typical engine.

* The [*Foundations of Game Engine Development*](https://foundationsofgameenginedev.com/) series by Eric Lengyel introduces fundamental topics rather than architecture, and it does so in enough detail to enable you to make proper implementations. The series is not finished yet, two books are currently available.

## Rendering

Rendering is one of the most important parts of an engine. There are often specialized roles for rendering, as opposed to generalist engine programmers. However, even as a generalist, you need to know the basics.

* [Getting Started In Computer Graphics](https://www.jeremyong.com/graphics/2024/05/19/getting-started-in-computer-graphics/) by Jeremy Ong.
* [Finding Your Home in Game Graphics Programming](https://alextardif.com/LearningGraphics.html) by Alex Tardif.
* [3D Computer Graphics Programming for Beginners](https://docs.google.com/document/d/1JwwLYxFMDwuxX4Sc3znE-8jVIQMW1LWjuvYeLpiVf_8/) by Angelo Pesce.

Introductory resources:
* Cem Yuksel's video lectures: [*Introduction to Computer Graphics*](https://www.youtube.com/playlist?list=PLplnkTzzqsZTfYh4UbhLGpI5kGd5oW_Hh) and [*Interactive Computer Graphics*](https://www.youtube.com/playlist?list=PLplnkTzzqsZS3R5DjmCQsqupu43oS9CFN).

Advanced resources:
* *GPU Zen 3: Advanced Rendering Techniques* by Wolfgang Engel et al.
* [*Mastering Graphics Programming with Vulkan*](https://github.com/PacktPublishing/Mastering-Graphics-Programming-with-Vulkan) by Marco Castorina and Gabriel Sassone.

Reference that covers a lot of topics:
* [*Real-Time Rendering*](https://www.realtimerendering.com/) by Tomas Akenine-Möller, Eric Haines, Naty Hoffman, Angelo Pesce, Michał Iwanicki, and Sébastien Hillaire. This itself contains many references to resources for the various presented techniques.

Resources for path tracing, useful to understand how rendering works by doing it all in software, without using the GPU:
* [*Ray Tracing in One Weekend*](https://raytracing.github.io/) by Peter Shirley is a short introduction.
* [*Physically Based Rendering: From Theory to Implementation*](https://www.pbrt.org/) by Matt Pharr, Wenzel Jakob, and Greg Humphreys. It is much more complete.

Online tools:
* [Shadertoy](https://www.shadertoy.com/), where people share shaders.

To use the GPU, you need to go through a graphics API. Modern engines use Direct3D 12 or Vulkan because they allow building multiple command buffers in parallel with multiple threads. However, Direct3D 11 is easier to learn. You should refer to the official documentations and specs, but below are listed additional resources.

Direct3D 11:
* *Practical Rendering & Computation with Direct3D 11* by Jason Zink, Matt Pettineo and Jack Hoxley.
* [Mārtiņš Možeiko's sample in C](https://gist.github.com/mmozeiko/5e727f845db182d468a34d524508ad5f).
* [Mārtiņš Možeiko's instancing example](https://gist.github.com/mmozeiko/3c9ba3a0ec0c54aff8b2dec7ac724208).
* d7samurai's samples: [part 1](https://gist.github.com/d7samurai/261c69490cce0620d0bfc93003cd1052), [2](https://gist.github.com/d7samurai/aee35fd5d132c51e8b0a78699cbaa1e4) and [3](https://gist.github.com/d7samurai/abab8a580d0298cb2f34a44eec41d39d).

Direct3D 12:
* [Microsoft's samples](https://github.com/microsoft/DirectX-Graphics-Samples).
* [*A Gentle Introduction to D3D12*](https://alextardif.com/DX12Tutorial.html) by Alex Tardif.
* [*GPU Memory Pools in D3D12*](https://therealmjp.github.io/posts/gpu-memory-pool/) by Matt Pettineo.

Vulkan:
* [*How to Learn Vulkan*](https://www.jeremyong.com/c++/vulkan/graphics/rendering/2018/03/26/how-to-learn-vulkan/) by Jeremy Ong.
* [*Vulkan in 30 minutes*](https://renderdoc.org/vulkan-in-30-minutes.html) by baldurk.
* [*API without Secrets: Introduction to Vulkan*](https://www.intel.com/content/www/us/en/developer/articles/training/api-without-secrets-introduction-to-vulkan-preface.html) by Pawel Lapinski.
* [*Vulkan Tutorial*](https://vulkan-tutorial.com/) by Alexander Overvoorde.
* [Vulkan C++ examples and demos](https://github.com/SaschaWillems/Vulkan) by Sascha Willems.
* *Vulkan Synchronization Primer*, [part 1](https://www.jeremyong.com/vulkan/graphics/rendering/2018/11/22/vulkan-synchronization-primer/) and [2](https://www.jeremyong.com/vulkan/graphics/rendering/2018/11/23/vulkan-synchonization-primer-part-ii/) by Jeremy Ong.
* [*Vulkan graphics backend*](https://github.com/keengames/vulkan_backend/tree/main) used at Keen Games.

Common to all modern APIs:
* [*Advanced API Performance*](https://developer.nvidia.com/blog/tag/advanced-api-performance) by Nvidia.
* [How to write a renderer for modern graphics APIs](https://blog.mecheye.net/2023/09/how-to-write-a-renderer-for-modern-apis/) by Jasper.

To understand the abstractions provided by the graphics APIs and use them most effectively, it helps to also learn about how GPUs work:
* [*A trip through the Graphics Pipeline*](https://fgiesen.wordpress.com/2011/07/09/a-trip-through-the-graphics-pipeline-2011-index/) by Fabian Giesen.
* [*Breaking Down Barriers*](https://therealmjp.github.io/posts/breaking-down-barriers-part-1-whats-a-barrier/) by Matt Pettineo.

## Physics

The most relevant field of physics for games is classical Newtonian mechanics, in particular rigid-body dynamics.

Chris Hecker has a list of resources: [*Physics References: An Annotated Bibliography for Rigid Body Dynamics*](https://www.chrishecker.com/Physics_References).

Introduction to dynamics:
* [*Game Physics*](https://gafferongames.com/post/integration_basics/) by Glenn Fiedler.
* [*Rigid Body Dynamics*](https://www.chrishecker.com/Rigid_Body_Dynamics) by Chris Hecker.
* [*An Introduction to Physically Based Modeling*](http://www.cs.cmu.edu/afs/cs/user/baraff/www/pbm/pbm.html) by Andrew Witkin, David Baraff, and Michael Kass.

Collision detection:
* [*Real-Time Collision Detection*](https://realtimecollisiondetection.net/) by Christer Ericson.

General introductory physics resources, not meant specifically for games or simulations, but with high quality explanations:
* [*The Feynman Lectures on Physics, Volume I*](https://www.feynmanlectures.caltech.edu/I_toc.html) by Feynman, Leighton, and Sands.
* [*Fundamentals of Physics I*](https://oyc.yale.edu/physics/phys-200) by Ramamurti Shankar. Also [on YouTube](https://www.youtube.com/playlist?list=PLFE3074A4CB751B2B).

## Networking

[*What is Rollback Netcode?*](https://bymuno.com/post/rollback) by Muno illustrates rollback netcode using gifs. It gives an intuition for some of the problems that networking can face in games.

Glenn Fiedler wrote many articles about networking in different series.
* [*Networking for Game Programmers*](https://gafferongames.com/categories/game-networking/).
* [*Networked Physics*](https://gafferongames.com/categories/networked-physics/).
* [*Building a Game Network Protocol*](https://gafferongames.com/categories/building-a-game-network-protocol/).

## Libraries

There are notable libraries known to be used by some engines. They satisfy requirements such as ease of integration, ease of debugging, good performance, ...

* [Dear ImGui](https://www.dearimgui.org/).
* [stb](https://github.com/nothings/stb).
* [EASTL](https://github.com/electronicarts/EASTL).
* [Jolt Physics](https://github.com/jrouwe/JoltPhysics).
* [Box2D](https://box2d.org/).

# 7. Starting on Your First Job

You do not need to know everything about engines to start working as an engine programmer.
And when you start, you will then be learning even more on the job.

Mike Acton gives his advice to new engine programmers in his talk [*Solving the Right Problems for Engine Programmers*](https://www.youtube.com/watch?v=4B00hV3wmMY).

An engine can be a very large program, and learning your way around your company's engine can be intimiading. Jeremy Ong gives advice in [*Grokking Big Unfamiliar Codebases*](https://www.jeremyong.com/game%20engines/2023/01/25/grokking-big-unfamiliar-codebases/).

Jeremy Ong also gives an overview of the important lenses through which he evaluates engines: [*How I Evaluate Game Engines*](https://www.jeremyong.com/game%20engines/2023/09/15/how-i-evaluate-game-engines/).

# Misc links

* [*Teach Yourself Programming in Ten Years*](http://norvig.com/21-days.html) by Peter Norvig, general advice about learning programming.
* [*Teach Yourself Computer Science*](https://teachyourselfcs.com/) by Oz Nova and Myles Byrne, a more general list of resources for self-learning computer science.
* [Handmade Network](https://handmade.network/), a community of programmers, many of whom have an interest in engine programming. Their Discord server is a good place to ask questions when you need help.

# FAQ

**Q**: How were the resources listed here chosen?

**A**: I used many of the resources myself when learning. Some have been recommended by other people, in which case I check that they are relevant, that they meet quality standards, and that they fill an obvious gap. I avoid adding many redundant resources, if I find a better one I replace the previous one.

**Q**: Is engine programming right for me?

**A**: If you just want to make games, you can use an existing engine such as Unreal. On the other hand, people drawn to making engines are in it for the pleasure of low-level programming, of knowing how everything works, of doing things themselves, and of achieving high quality results. You may find the resources listed here useful even if you do not plan on becoming an engine programmer.

**Q**: Who wrote this page?

**A**: I'm Radek Jurga, I work as an engine programmer. I studied physics and then learned programming on my own, using many of the resources listed above. I initially wrote this page for a friend who I was mentoring. At the time, he was a physician, and using this guide he succesfully changed career to AAA game development. I joined the same studio and we now work together. This page is online in the hope that other people will find it useful too.
