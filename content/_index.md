+++
title =  "Learn Game Engine Programming"
date = 2022-08-25T21:30:04+08:00
draft = false
+++

This is a list of self-learning resources for game engine programming. It is not exhaustive, there are many more things to learn, but it will get you started.

# 1. Programming Basics

Engines are mostly written in C++ because it maps somewhat directly to how the CPU works, which allows to achieve high performance.

The [*Handmade Hero*](https://handmadehero.org/) video series by Casey Muratori shows how to make an engine from scratch in C, which is a subset of C++. However, Handmade Hero's intro to C is brief and likely insufficient if you do not already have enough programming experience. If that is your case, complement it with other resources.

Stack Overflow has a [list of C++ books](https://stackoverflow.com/questions/388242/the-definitive-c-book-guide-and-list), including two introductory ones. Of these, *C++ Primer* is appropriate if you already programmed before, and *Programming: Principles and Practice Using C++* if you never did.

When you need to quickly look something up, an online reference for C and C++ is [cppreference.com](https://en.cppreference.com/). If you prefer something written in a more informal style and that is easier to read, [*The C++ Programming Language*](https://www.stroustrup.com/4th.html) by Bjarne Stroustrup.

# 2. Programming Best Practices

C++ is a huge language with many parts and features that can be used in many different ways. Engine programmers often only use some parts of the language, and only in some ways.

[*The Rules of Programming: How to Write Better Code*](https://www.oreilly.com/library/view/the-rules-of/9781098133108/) by Chris Zimmerman explains the programming practices used at the video game studio Sucker Punch Productions where they make their own engine.

Additional examples of practices sometimes followed:
* [John Carmack on Inlined Code](http://number-none.com/blow/john_carmack_on_inlined_code.html).
* [John Carmack on Functional Programming in C++](http://www.sevangelatos.com/john-carmack-on/).

On the other hand, here are examples of C++ features and practices that are sometimes avoided, with links to typical justifications:
* Object-oriented features such as virtual functions: [*"Clean" Code, Horrible Performance*](https://www.computerenhance.com/p/clean-code-horrible-performance) by Casey Muratori.
* The STL: [Twitter thread](https://twitter.com/m_ninepoints/status/1497768472184430600) by Jeremy Ong. Many engines use their own replacement of the STL, such as the [Electronics Arts Standard Template Library](https://github.com/electronicarts/EASTL) whose documentation contains [justifications](https://github.com/electronicarts/EASTL/blob/master/doc/FAQ.md#info6-why-is-there-eastl-when-there-is-the-stl).
* Exceptions: [Hacker News comment](https://news.ycombinator.com/item?id=28164247) by Walter Bright.

# 3. Algorithms and Data Structures

Algorithms and data structures are fundamental to solving problems with code. They are used everywhere in engines. You need to know their characteristics.

A book that uses C to teach them is [*The Algorithm Design Manual*](https://www.algorist.com/) by Steven Skiena.

A website with fun exercises to practice is [*Advent of Code*](https://adventofcode.com/).

Further reading:
* [*I've been writing ring buffers wrong all these years*](https://www.snellman.net/blog/archive/2016-12-13-ring-buffers/) by Juho Snellman.

# 4. Computer Architecture and Performance

Engine programming requires a good understanding of how computers work in order to achieve the high performance required for real-time interactive games.

## Basics

The [*Performance-Aware Programming* Series](https://www.computerenhance.com/p/welcome-to-the-performance-aware) by Casey Muratori teaches everything that you really need to know well. The course materials are currently in production, with a weekly release schedule.

For a book, [*Computer Systems: A Programmer's Perspective*](http://csapp.cs.cmu.edu/) by Randal E. Bryant and David R. O'Hallaron. It has a slightly broader scope, introducing topics in operating systems, networking, and systems programming on Linux. Most engine programming is done on Windows, but the concepts covered in the book are fundamental enough to carry over. However, it does requires Linux for doing the labs.

[*Algorithms for Modern Hardware*](https://en.algorithmica.org/hpc/) by Sergey Slotin is not finished, so it currently doesn't cover as many topics with the same depth, but can be useful nontheless.

Misc useful links:
* Online reference for intrinsics: [Intel Intrinsics Guide](https://www.intel.com/content/www/us/en/docs/intrinsics-guide/index.html).
* Online tool to see the floating point representation of a number: [Float Exposed](https://float.exposed/).

## Assembly

You do not necessarily need to know how to write assembly yourself, but you need to know how to read it. One of the main uses is to verify that the compiler did what you expect with your code, for example in terms of optimization.

[Compiler Explorer](https://godbolt.org/) is a tool that lets you see the assembly that various compilers produce from your code snippets. You can learn a lot just by playing with it.

The basic resources listed previously already cover assembly, but more specific resources are listed here.

The [*Applied Reverse Engineering*](https://revers.engineering/applied-reverse-engineering-series/) series by Daax Rynd is incomplete, but does cover the basics.

The book [*Reverse Engineering for Beginners*](https://beginners.re/) by Dennis Yurichev is more complete.

Online references:
* x86 instructions: [www.felixcloutier.com/x86/](https://www.felixcloutier.com/x86/).
* Performance characteristics of x86 instructions: [uops.info](https://uops.info/).

## Data-Oriented Design

A programming approach often adopted in engine programming is known as data-oriented design. It aims at increasing performance by organizing programs to take advantage of the way that modern CPUs work, in particular with respect to caching. This approach is introduced in:
* [*Efficiency with Algorithms, Performance with Data Structures*](https://www.youtube.com/watch?v=fHNmRkzxHWs) by Chandler Carruth.
* [*Optimizable Code*](https://deplinenoise.wordpress.com/2013/12/28/optimizable-code/) by Andreas Fredriksson.
* [*Data-Oriented Design and C++*](https://www.youtube.com/watch?v=rX0ItVEVjHc) by Mike Acton.

## Advanced

Knowing the basics well is enough as a beginning generalist engine programmer. But if you want to specialize in optimization, *Computer Architecture: A Quantitative Approach* by John L. Hennessy and David A. Patterson gives a lot more details about the way hardware works.

Agner Fog wrote several advanced [*optimization manuals*](https://www.agner.org/optimize/#manuals).

# 5. Engine Programming

Finally, we have enough fundamental knowledge and we now turn to engines. But note that you do not need to finish learning all the fundamentals before starting to learn about engines.

## General

[*Game Engine Architecture*](https://www.gameenginebook.com/) by Jason Gregory gives a broad overview of how engines are organized. It will make you familiar with the different parts of a typical engine.

The [*Foundations of Game Engine Development*](https://foundationsofgameenginedev.com/) series by Eric Lengyel introduces fundamental topics rather than architecture, and it does so in a lot of detail, enabling you to make proper implementations. The series is not finished yet, two books are currently available. If you find the math of volume 1 not introductory enough, refer to the math appendix of this guide for more complete resources.

## Rendering

Rendering is one of the most important parts of an engine. There are often specialized roles for rendering, as opposed to generalist engine programmers. However, even as a generalist, you need to know the basics.

Different people give advice about learning graphics programming:
* [Alex Tardif](https://alextardif.com/LearningGraphics.html).
* [Jeremy Ong](https://twitter.com/m_ninepoints/status/1215429886715629569).

Broad introductory resources:
* [*Learn OpenGL*](https://learnopengl.com/) by Joey de Vries.
* [*Foundations of Game Engine Development, Volume 2: Rendering*](https://foundationsofgameenginedev.com/) by Eric Lengyel. It assumes you can already use some graphics API.
* Cem Yuksel's video lectures: [*Introduction to Computer Graphics*](https://www.youtube.com/playlist?list=PLplnkTzzqsZTfYh4UbhLGpI5kGd5oW_Hh) and [*Interactive Computer Graphics*](https://www.youtube.com/playlist?list=PLplnkTzzqsZS3R5DjmCQsqupu43oS9CFN).

A general reference that covers a lot of topics is [*Real-Time Rendering*](https://www.realtimerendering.com/) by Tomas Akenine-Möller, Eric Haines, Naty Hoffman, Angelo Pesce, Michał Iwanicki, and Sébastien Hillaire. This itself contains many references to resources for the various presented techniques.

Resources for path tracing, useful to learn how rendering works by doing it all in software, without using the GPU:
* [*Ray Tracing in One Weekend*](https://raytracing.github.io/) by Peter Shirley is a short introduction.
* [*Physically Based Rendering: From Theory to Implementation*](https://www.pbrt.org/) by Matt Pharr, Wenzel Jakob, and Greg Humphreys. It is much more complete.

[Inigo Quilez's web site](https://iquilezles.org/) contains some rendering tutorials. He also co-created [Shadertoy](https://www.shadertoy.com/), where people share their shaders.

To use the GPU, you need to go through a graphics API. OpenGL and Direct3D 11 are the easiest to start with. Their successors, Vulkan and Direct3D 12, are more complex, but these are what modern engines use because they allow building multiple command buffers in parallel with multriple threads. Below are resources for these APIs.

OpenGL:
* [*Learn OpenGL*](https://learnopengl.com/) by Joey de Vries.

Direct3D 11:
* [The official documentation](https://learn.microsoft.com/en-us/windows/win32/direct3d11/atoc-dx-graphics-direct3d-11).
* d7samurai's samples: [part 1](https://gist.github.com/d7samurai/261c69490cce0620d0bfc93003cd1052), [2](https://gist.github.com/d7samurai/aee35fd5d132c51e8b0a78699cbaa1e4) and [3](https://gist.github.com/d7samurai/abab8a580d0298cb2f34a44eec41d39d).
* [Mārtiņš Možeiko's sample in C](https://gist.github.com/mmozeiko/5e727f845db182d468a34d524508ad5f).

Vulkan:
* [The specification](https://registry.khronos.org/vulkan/specs/1.1/html/vkspec.html).
* [*How to Learn Vulkan*](https://www.jeremyong.com/c++/vulkan/graphics/rendering/2018/03/26/how-to-learn-vulkan/) by Jeremy Ong.
* [*Vulkan in 30 minutes*](https://renderdoc.org/vulkan-in-30-minutes.html) by baldurk.
* [*API without Secrets: Introduction to Vulkan*](https://www.intel.com/content/www/us/en/developer/articles/training/api-without-secrets-introduction-to-vulkan-preface.html) by Pawel Lapinski.
* [*Vulkan Tutorial*](https://vulkan-tutorial.com/) by Alexander Overvoorde.
* [Vulkan C++ examples and demos](https://github.com/SaschaWillems/Vulkan) by Sascha Willems.
* *Vulkan Synchronization Primer*, [part 1](https://www.jeremyong.com/vulkan/graphics/rendering/2018/11/22/vulkan-synchronization-primer/) and [2](https://www.jeremyong.com/vulkan/graphics/rendering/2018/11/23/vulkan-synchonization-primer-part-ii/) by Jeremy Ong.

Direct3D 12:
* [The official API documentation](https://learn.microsoft.com/en-us/windows/win32/direct3d12/direct3d-12-graphics).
* [The specification](https://microsoft.github.io/DirectX-Specs/).
* [Microsoft's samples](https://github.com/microsoft/DirectX-Graphics-Samples).
* [*DX12 Do's And Don'ts*](https://developer.nvidia.com/dx12-dos-and-donts) by Nvidia.
* [*Learning D3D12*](https://www.jendrikillner.com/post/d3d12-learning-plan/) by Jendrik Illner.
* [*A Gentle Introduction to D3D12*](https://alextardif.com/DX12Tutorial.html) by Alex Tardif.
* [*GPU Memory Pools in D3D12*](https://therealmjp.github.io/posts/gpu-memory-pool/) by Matt Pettineo.

To understand the abstractions provided by the graphics APIs and use them most effectively, it helps to also learn about how GPUs work:
* [*A trip through the Graphics Pipeline*](https://fgiesen.wordpress.com/2011/07/09/a-trip-through-the-graphics-pipeline-2011-index/) by Fabian Giesen.
* [*Breaking Down Barriers*](https://therealmjp.github.io/posts/breaking-down-barriers-part-1-whats-a-barrier/) by Matt Pettineo.

## Physics

The most relevant field of physics for games is classical Newtonian mechanics, in particular rigid-body dynamics. Optics can be useful for understanding rendering techniques, but resources are not provided here.

Chris Hecker has a list of resources: [*Physics References: An Annotated Bibliography for Rigid Body Dynamics*](https://www.chrishecker.com/Physics_References).

Introduction to dynamics:
* [*Game Physics*](https://gafferongames.com/post/integration_basics/) by Glenn Fiedler.
* [*Rigid Body Dynamics*](https://www.chrishecker.com/Rigid_Body_Dynamics) by Chris Hecker.

In-depth dynamics:
* [*An Introduction to Physically Based Modeling*](http://www.cs.cmu.edu/afs/cs/user/baraff/www/pbm/pbm.html) by Andrew Witkin, David Baraff, and Michael Kass.
* *Dynamic Simulations of Multibody Systems* by Murilo G. Coutinho.

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

Engines usually use few libraries. However, there are notable ones known to be commonly used. They satisfy requirements such as ease of integration, ease of debugging, good performance, ...

* [Dear ImGui](https://www.dearimgui.org/).
* [stb](https://github.com/nothings/stb).
* [EASTL](https://github.com/electronicarts/EASTL).

# 6. Starting on Your First Job

You do not need to know everything about engines to start working as an engine programmer.
And when you start, you will then be learning even more on the job.

Mike Acton gives his advice to new engine programmers in his talk [*Solving the Right Problems for Engine Programmers*](https://www.youtube.com/watch?v=4B00hV3wmMY).

An engine can be a very large program, and learning your way around your company's engine can be intimiading. Jeremy Ong gives advice in [*Grokking Big Unfamiliar Codebases*](https://www.jeremyong.com/game%20engines/2023/01/25/grokking-big-unfamiliar-codebases/).

# Appendices

## A. Math

Some parts of an engine can require a lot of math, such as rendering and physics. The most important fields are trigonometry, calculus, and linear algebra.

Calculus:
* [*Calculus GREEN*](https://www.youtube.com/playlist?list=PL8erL0pXF3JaFSMdokheNMvTa96jdc4GU) by Robert Ghrist, only the first volume is currently available.
* [*Calculus BLUE*](https://www.youtube.com/playlist?list=PL8erL0pXF3JYm7VaTdKDaWc8Q3FuP8Sa7) by Robert Ghrist.

Introductory linear algebra:
* [*Essence of Linear Algebra*](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) by 3Blue1Brown.
* [*Calculus BLUE Vol 1 : Vectors & Matrices*](https://www.youtube.com/playlist?list=PL8erL0pXF3JYm7VaTdKDaWc8Q3FuP8Sa7) by Robert Ghrist.
* [*Linear Algebra*](https://ocw.mit.edu/courses/18-06sc-linear-algebra-fall-2011/) by Gilbert Strang.
* [*Introduction to Applied Linear Algebra – Vectors, Matrices, and Least Squares*](https://web.stanford.edu/~boyd/vmls/) by Stephen Boyd and Lieven Vandenberghe.

Rigorous linear algebra:
* [*Linear Algebra Done Right*](https://linear.axler.net/) by Sheldon Axler.
* [*Linear Algebra Done Wrong*](https://www.math.brown.edu/streil/papers/LADW/LADW.html) by Sergei Treil.

## B. Misc links

* [*Teach Yourself Programming in Ten Years*](http://norvig.com/21-days.html) by Peter Norvig, general advice about learning programming.
* [*Teach Yourself Computer Science*](https://teachyourselfcs.com/) by Oz Nova and Myles Byrne: a more general list of resources for self-learning computer science.
* [Handmade Network](https://handmade.network/), a community of programmers, many of whom have an interest in engine programming. Their Discord server is a good place to ask questions when you need help.

# FAQ

**Q**: How were the resources listed here chosen?

**A**: I used many (but not all) of the resources myself. Some have been recommended by other people, in which case I at least take a look to check if they are relevant and if they meet basic quality standards.

**Q**: Is engine programming right for me?

**A**: If you just want to make games, use an existing engine such as Unreal or Unity. On the other hand, people drawn to making engines are in it for the pleasure of low-level programming, of knowing how everything works and of doing things themselves. You may find the resources listed here useful even if you do not plan on becoming an engine programmer.

**Q**: Who wrote this page?

**A**: I'm Radek Jurga, I work as an engine programmer. I studied physics and then learned programming on my own, using many of the resources listed above. I wrote this primarily for a friend who I am mentoring, he is a physician in the process of changing career to also become an engine programmer, goal toward which he is making excellent progress. I hope that other people will find the page useful too.
