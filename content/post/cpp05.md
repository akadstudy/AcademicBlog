---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Exercise 1"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T13:56:01+02:00
lastmod: 2020-09-17T13:56:01+02:00
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
projects: []
---

## Compiling Our First Application

In this exercise, we are going to compile and run our first C++ application. We're going to be using an online compiler throughout the course (and the reasons for doing so will be explained after this exercise) but for now, let's get that compiler up and running. Perform the following steps to complete the exercise:

> **Note:** The code file for this exercise can be found [here](Link).

1. Head [cpp.sh](http://cpp.sh/) and take a look around. This is the compiler that we'll be using. Once you go to the address, you should observe the following window:

**Options**: This allows us to change various compilation settings. We won't be touching this.
**Compilation**: This shows us the status of our program. If there are any compilation issues, they'll be shown here so we can address them.
**Execution**: This window is our console, allowing us to interact with the application. We'll input our values here and view the output of the application.
For our first program, we'll run the "**Hello World!**" application we deconstructed in the preceding section.

2. Type the following code into the code window, replacing all the content that's already there, and then hit **Run**:

```c++
//Hello world example.
#include <iostream>

int main()
{
    std::cout <<"Hello World!";
    return 0;
}
```

As you can see, the console now contains the text Hello World!, meaning our program ran without issue:

Try changing the text to something unique and run the program again.

> Note: Here is a partial list of online C++ compilers you can use while working on the exercises. If the one you are using becomes sluggish, or you can't find it at all, try another. Online compilers are useful because they reduce the amount of stuff you have to learn to almost nothing beyond the programming language.

- **Tutorialspoint C++ compiler**: This website allows you to compile a C++ program contained in a single file. It prints error messages from the operating system. You can find it [here](https://www.tutorialspoint.com/compile_cpp_online.php).
- **cpp.sh**: This website allows you to pick a C++ language version and warning level, and compile a single file. However, it does not print error messages from the operating system. You can find it [here](http://cpp.sh/).
- **godbolt compiler explorer**: This website allows you to compile a single file on many different compilers and shows the output assembly language; its UI is a little subtle for some tastes. It prints error messages from the operating system. You can find it [here](https://godbolt.org/).
- **coliru**: This website allows you to compile a single file. It prints error messages from the operating system. You can find it [here](http://coliru.stacked-crooked.com/).
- **repl.it**: This website allows you to compile multiple files. You can find it [here](https://repl.it/languages/cpp).
- **Rextester**: This website lets you compile a single file using Microsoft Visual C++. You can find it [here](https://rextester.com/).