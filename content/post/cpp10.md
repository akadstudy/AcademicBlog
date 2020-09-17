---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Basic I/O Statements"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T22:24:01+02:00
lastmod: 2020-09-17T22:24:01+02:00
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

# Basic I/O Statements

I/O stands for **input/output** and is how we get information in and out of our programs. This can take many forms, from inputting text via a keyboard, to clicking buttons with our mouse, to loading a file, and so on. In this chapter, and in general moving forward, we're going to be sticking with text input/output. For this, we'll use the **iostream** header.

Throughout this section, we'll be reading directly from input with little to no data validation. In a working application, however, input would be strictly validated to ensure it's of the correct format, among other things. Our lack of this is strictly for example purposes only.

The **iostream** header contains everything we need to interface with our applications via the keyboard, allowing us to get data in and out of our application. This is accomplished through the **std::cin** and **std::cout** objects.

> **Note**: The **std::** prefix here denotes a namespace. This will be looked at in more depth later in the course, but for now we can just know they're used to group code.

There's a couple of ways we can read data from our keyboard. First, we can use **std::cin** with the extraction operator:

`std::cin >> myVar`

This will put your input into the **myVar** variable and works for both string and integer types.

Observe the following code that has an **std::cin** object included:

```C++
// Input example.
#include <iostream>
#include <string>

int main()
{
    std::string name;
    int age;

    std::cout << "Please enter your name: ";
    std::cin >> name;
    std::cout << "Please enter you age: ";
    std::cin >> age;

    std::cout << name << std::endl;
    std::cout << age;
}
```

If we run this code in our compiler, we can see that we can enter our details and have them printed back to us:

If you tried to enter a name with a space in, you'll have run into an issue where only the first name was captured. This gives us more insight into how **std::cin** is working; namely that it will stop capturing input when it encounters a terminating character (space, tab, or new line). We can see now why only our first name was captured properly.

It's also useful to know that extractions, the **>>** operator, can be chained. This means that the following two examples of code are equivalent:

**Example 1:**

```C++
std::cin >> myVar1;
std::cin >> myVar2;
```

**Example 2:**

```C++
std::cin >> myVar1 >> myVar2;
```

To avoid our strings being cut off when a terminating character, such as space, is encountered, we can pull the entirety of the users input into a single variable by using the **getline** function. Let's update our code using this function to get the user's name:

```C++
std::cout << "Please enter your name: ";
getline(std::cin, name);
```

If we run the code again, we can now see that we're able to use spaces in our name and **getline()** will capture the whole input. Using **getline()** is nicer because it means we don't have to worry about the line issues that can come with using **cin** extraction directly.

When we use **getline()**, we read our user's input into a string, but that doesn't mean we can't use it to read integer values. To convert a string value into its integer equivalent, we have the **std::stoi** function. For example, the string **"1"** would be returned as **int** **1**. Combining it with **getline()** is a good way to parse integer inputs:

```C++
std::string inputString = "";
int inputInt = 0;

getline(std::cin, inputString);
inputInt = std::stoi(inputString);
```

Regardless of which method we use, we need to ensure that we handle strings and numerical values correctly. For example, perhaps we have some code that expects the user to input a number:

```C++
int number;

std::cout << "Please enter a number between 1-10: ";
std::cin >> number;
```

If the user inputs a string here, maybe they type **five** instead of inputting the number, the program won't crash, but our **number** variable won't be assigned a value. This is something we need to be aware of when getting input from our users. We need to ensure it's of the correct format before we try to use it in our programs.

Outputting text is as simple as making a call to **std::cout**, using the insertion operator, **<<**, to pass our data. This will accept both string and numerical values, so both the following code snippets will work as intended:

```C++
std::cout << "Hello World";
std::cout << 1;
```

As with the extraction operation, the insertion operator can be chained to build more complex outputs:

`std::cout << "Your age is " << age;`

Finally, when outputting text there are times where we want to either start a new line or insert a blank one. For this, we have two options, **\n** and **std::endl**. Both of these will end the current line and move to the next. Given this, the following code snippets give the same output:

```C++
std::cout << "Hello\nWorld\n!";
std::cout << "Hello" << std::endl << "World" << std::endl << "!"<< std::endl;
```

As mentioned earlier, there are other types of input and output associated with applications; however, most of the time, IO will be facilitated through some form of UI. For our purposes, these two basic objects, **std::cin/std::cout**, will suffice.

We will apply our knowledge of the **getline()** method and the **std::cin**, **std:cout**, and **std::endl** objects in the next exercise.