---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Advantages of C++"
subtitle: ""
summary: ""
authors: []
tags: [Cpp]
categories: []
date: 2020-09-17T06:19:12+02:00
lastmod: 2020-09-17T06:19:12+02:00
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

## Advantages of C++

Before we dive into the structure of a C++ program, let's have a look at a few key benefits of the language:

- **Performance**: By putting the programmer close to the hardware, C++ allows us to write very efficient programs. Along with low-level memory access, the abstraction between code and what the machine will do is smaller than in most other languages, meaning you can manipulate the system better.
- **Portability**: C++ can be cross-compiled to a wide array of platforms, and runs on everything from watches to televisions. If you're writing an application or library for more than one platform, C++ shines.
- **General purpose**: C++ is a general-purpose programming language, and is used in everything from video games to enterprise. With a rich feature set spanning everything from direct memory management to classes and other Object-Oriented Programming (OOP) principles, you can make C++ work for you.
- **Large libraries**: Since the language is used in so many applications, there's an abundance of libraries to choose from. With hundreds of open source repositories, the wealth of information (and the support systems that come with it) is vast.

C++ is a double-edged sword, however, and as the famous saying goes, "With great power comes great responsibility". C++ gives you enough room to do great things, but also to get yourself into trouble if used incorrectly. Bjarne himself once said of the language, "C makes it easy to shoot yourself in the foot; C++ makes it harder, but when you do it blows your whole leg off." That's not to say by any means that C++ should be avoided, just that it should be used deliberately and with consideration—something the following chapter will impart.

## Anatomy of a C++ Application

With a brief understanding of the history of the language, we're going to start our journey by delving into a basic C++ program to see what we're working with. There's no more fitting a start than Hello World!. This famous program prints the words Hello World! to the console, and has served as the starting point for scores of programmers before you. While basic, it contains all the key components of a C++ application, so will prove a great example for us to de-construct and learn from.

Let's start by taking a look at the program in its entirety:

```c++
// Hello world example.
#include <iostream>

int main()

{
    std::cout << "Hello World!";
    return 0;
}
```

Consisting of just seven lines of code, this small program contains everything we need to look at the basic anatomy of a C++ program. We're going to cover each aspect of this program in more detail over the coming chapters, so don't worry if not everything makes perfect sense as we break this program down. The aim here is simply to familiarize ourselves with some core concepts before covering them in more detail as we progress.

Starting from the top, we have a **preprocessor directive**:

`#include <iostream>`

Preprocessor directives are statements that allow us to perform certain operations before the program is built. The include directive is a very common directive that you'll see in most C++ files, and it means "copy here." So, in this case, we're going to copy the contents of the iostream header file into our application, and in doing so, allow ourselves to use input/output functionality it provides.

Next, we have our entry point, **main()**:

`int main()`

The main() function is where your C++ application will kick-off. All applications will have this function defined and it marks the start of our application—the first code that will be run. This is typically your outer-most loop because as soon as the code in this function is complete, your application will close.

Next, we have an IO statement that will output some text to the console:

`std::cout << "Hello World!";`

Because we have included the iostream header at the start of our application, we have access to various input and output functionality. In this case, std::cout. cout allows us to send text to the console, so when we run our application, we see that the text "Hello World!" is printed. We'll cover data types in more detail in the coming chapters.

Finally, we have a return statement:

`return 0;`

This signals that we're done in the current function. The value that you return will depend on the function, but in this case, we return 0 to denote that the application ran without error. Since this is the only function in our application, it will end as soon as we return.

And that's our first C++ application; there's not too much to it. From here, the sky is the limit, and we can build applications that are as big and complex as we like, but the fundamentals covered here will stay the same throughout.

Seeing this application typed out is one thing, but let's get it running in our first exercise.