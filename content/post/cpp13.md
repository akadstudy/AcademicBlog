---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Exercise 4"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-18T00:11:13+02:00
lastmod: 2020-09-18T00:11:13+02:00
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

# Functions

In this exercise, we're going to define and use a function that will output the larger of two numbers. This function will require a return type and two parameters. Perform the following steps to complete the exercise:

1. Declare the function, assigning its return type, name, and parameters:

```C++
#include<iostream>
int Max(int a, int b)
```
As we saw earlier, if we were purely declaring this function in a header file, we would add a semicolon to the end of that and define it elsewhere. Since that's not the case, however, we open our curly braces straight away and define our functionality.

2. Define the behavior of the function. We want to return the number that has the highest value, so the logic for this is easy, as shown in the following example:

```C++
int Max(int a, int b)
{
    if (a > b)
    {
        return a;
    }
    else
    {
        return b;
    }
}
```

3. Now all we need to do is get two numbers from our users. We've covered IO earlier in this chapter, so we should be comfortable with that:

```C++
int main()
{
    int value1 = 0;
    int value2 = 0;

    std::cout << "Please input number 1: ";
    std::cin >> value1;

    std::cout << "Please input number 2: ";
    std::cin >> value2;
```

4. Finally, we need to output the answer to the user. We've covered this before as well, but this time, instead of using a variable in our **cout** statement, we'll make a call to our new function, passing in the user's numbers:

```C++
std::cout << "The highest number is " << Max(value1, value2);
}
```

5. The complete code looks like this:

```C++
// IO Exercise.
#include <iostream>
#include <string>

int Max(int a, int b)
{
    if (a > b)
    {
        return a;
    }
    else
    {
        return b;
    }
}

int main()
{
    int value1 = 0;
    int value2 = 0;
    
    std::cout << "Please input number 1: ";
    std::cin >> value1;
    std::cout << "Please input number 2: ";
    std::cin >> value2;
    std::cout << "The highest number is " << Max(value1, value2);
}
```

6. Run this in the compiler and test it with some numbers.