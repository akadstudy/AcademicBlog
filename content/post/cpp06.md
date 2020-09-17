---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "C++ Build Pipeline"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T14:51:54+02:00
lastmod: 2020-09-17T14:51:54+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [cpp]
---

## C++ Build Pipeline

Before we go any further, let's take a moment to discuss the build pipeline. This is the process that turns the code that we write into an executable that our machines are capable of running. When we write our C++ code, we're writing a highly abstracted set of instructions. Our machines don't natively read C++ as we do, and likewise, they're unable to run our C++ files as we write them. They first have to be compiled into an executable. This process consists of a number of discrete steps and transforms our code into a more machine-friendly format along the way:

- **Preprocessor**: As the name implies, it runs through our code before it's compiled, resolving any preprocessor directives that we may have used. These include things such as **include** statements, which we saw previously, and others such as macros and defines that we'll look at later in this lesson. Our files are still human-readable at this point. Think of the preprocessor as a useful editor that will run through your code, doing all the little jobs you've marked, preparing our code for the next step—the compiler.
- **Compilation**: The compiler takes our human-readable files and converts them into a format that the computer can work with—that is, binary. These are stored in object files that end with **.o** or **.obj**, depending on the platform. Consider the small **Hello World !** application we dissected earlier. All that code lives in a single file, **main.cpp**. If we were to pass that to a compiler, we would get back **main.o**; an object file containing the binary version of our source code that the machine can run. This isn't quite ready to run yet, and you can't directly execute an object file. Before we can execute our application, we need to look at the final step of the pipeline—the linker.
- **Linker**: The linker is the last step in producing our executable. Once the compiler has turned our source code into binary objects, the linker comes through and links them all together, putting together our final executable.
- The aforementioned steps have been visualized in the following process flow diagram:



These three steps are what every C++ application goes through, be it a single-file program such as the **"Hello World!"** program we've already discussed, or a multi-thousand-file application that you might see in real-world applications; these fundamental steps remain the same.

Different operating systems have different toolsets that perform these actions, and covering them all would not only take focus away from writing C++ itself, but potentially create different experiences, depending on the setup, especially because they're always changing. That's why in this course we'll be using an online compiler. Not only can we jump straight into writing code, but we can be sure that everyone will have the same results.

This overview of these processes has hopefully provided a solid overview of the fundamentals, so that when you do look to compile your applications in the future, the process will be familiar and you'll understand what's going on behind the scenes.