---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "C++ Keywords"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T20:13:48+02:00
lastmod: 2020-09-17T20:13:48+02:00
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

# C++ Keywords

**Keywords** are words that are reserved by C++. Thus, we cannot use them in our applications for anything other than their intended purposes. For example, a common keyword is **if**, so you would not be able to define a variable or function of that name. It's these keywords that structure the C++ language, and it's through their use that we instruct our program on what it should be doing.

There are many keywords defined in the language, and covering them all at this early stage is not necessary. Instead, let's take a look at the keywords that we'll encounter over the coming chapters.

Some of these words define basic types, (**bool, char, int**, and so on), some of them are statements to define program flow (**if, else, switch**, and so on), and others define objects and scope (**class, struct, namespace**, and so on).

We'll be using these throughout the course, but for now we just need to know that these words are reserved by C++. You'll be able to tell because most modern text editors will highlight these words thereby making them stand out. Let's take a look at how keywords are distinguished in our code editor. Observe the following program:

```C++
// Keywords example.
#include <iostream>
#include <string>

int main()
{
    // Data type keywords.
    int myInt = 1;
    double myDouble = 1.5;
    char myChar = 'c';
    bool myBool = true;

    // Program flow keywords.
    if (myBool)
    {
        std::cout << "true";
    }
    else
    {
        std::cout << "false";
    }

    struct myStruct
    {
        int myInt = 1;
    };
}
```

On the compiler window, the preceding code would appear as follows:


We can see that the keywords in this program are given special presentation in the editor, usually a different color, to denote their status. This will differ between IDEs.

> **Note**: IDE stands for Integrated Development Environment and is the software that we use to develop our applications. Example IDEs include Visual Studio and CLion.

## Keyword Example

Running through each keyword individually isn't necessary. We'll cover them as we go, but we can quickly take a look at some common keyword groups and what they do.

Type keywords denote the basic variable types provided by C++. These include **int**, **bool, char, double**, and **float**:

```C++
int myInt = 1;
char myChar = 'a';
bool myBool = true;
double myDouble = 1.5;
float myFloat = 1.5f;
```

Program flow keywords allow us to structure the logic of the application. These include **if, else, then**, and **switch**, as shown in the following snippet:

```C++
if (expression)
{
  // do this
}
else
{
  // do this instead.
}
```

Access modifiers determine what other classes and components can and can't see our C++ variables and functions. When building classes (something we'll look at shortly) we have three to choose from: **public, protected**, and **private**. The correct use of these modifiers plays a big part in building robust systems, ensuring our data and functionality isn't open to abuse or dangerous misuse. Here is an example:

```C++
class MyClass()
{
    public:
        int var1; // Accessible to the class, everything that can see MyClass.
    protected:
        int var2; // Accessible to the class, and any child classes.
    private:
        int var3; // Accessible to the class only.
}
```

Modifier types change the properties of our variables. These include **const, static, signed**, and **unsigned**. By putting these in front of our variables and functions, we can change the way they behave in our application, as shown in the following example:

```C++
unsigned int var1 = 1; // Unsigned means it can only be positive.
signed int var2 = -1; // Signed can be both positive or negative.
const std::string var3 = "Hello World"; // Const means the value cannot be modified 
static char var4 = 'c'; // Static means the value is shared between all instances of a given class.
```