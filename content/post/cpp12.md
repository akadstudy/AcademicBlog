---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Functions"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T23:00:20+02:00
lastmod: 2020-09-17T23:00:20+02:00
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

**Functions** in C++ encapsulate our code into logical units of functionality. We can then call these functions instead of having duplicate code throughout our project. For example, consider a small application that asks users for their name, greets them, and then stores that name in a list, as shown in the following snippet:

```C++
// Get name.
std::cout << "Please enter your name: " << "\n";
getline(std::cin, name);
std::cout << "Welcome " << name << ".\n";
names.push_back(name);
```

This is code that we will probably want to call multiple times during our application's lifetime, so it is a good candidate to be put into a function. The benefit in doing so is that it reduces duplicate code through our applications, giving us a single place where we can maintain the code and fix any bugs. If it was duplicated throughout the code base, anytime you want to upgrade it or fix something, you'd have to find all instances and do it to each.

A function is split into two parts: a **declaration** and a **definition**. In a function declaration, you're declaring the most basic information about how that function will work–namely–the type of value the function will return, the name of the function, and any parameters. The actual logic of the function's behavior is then dictated by the definition. Let's break a function declaration down.

A function is declared as follows:

`return_type function_name(parameters);`

- **return_type**: This is the type of value that you will return from the function. You can also return **void**, a C++ keyword, if you don't want to return anything. For example, if you had a function that added two numbers together, the return type might be **integer**.
- **function_name**: This is the name of the function and is how you'll reference it in code.
- **parameters**: These are an optional set of values that you pass into a function. Again, taking the example of adding two numbers, you would have two **integer** parameters: your first and second numbers.

This declaration usually lives in a header file (**.h**) along with other functions declarations, and they're then defined in a **.cpp** file. *This is why we see the #include directive so often*. We declare our objects' functionality in header files, then actually define how they work in **.cpp** files. We usually separate these into individual files because it allows us to hide implementation details. It's often the case that header files are made public, so we can see an object's functionality and use it, but the exact implementation of that function is kept private.

> **Note**: We're not going to worry about this for now. Since we're working in a single file, we're just going to define and declare functions at the same time, not separately.

Taking this back to our previous example, we can take the snippet of code that allows a user to input their name, and define it in a function as shown in the following snippet:

```C++
void GetNextName()
{
    std::string name;
    std::cout << "Please enter your name: " << "\n";
    getline(std::cin, name);
    std::cout << "Welcome " << name << ".\n";
    names.push_back(name);
}
```

Now, each time we need this functionality, we can just call this function instead. The function provides its own variable, **name**, for us to use, but note that the **names** variable is being used from the main program. This is possible as it's within scope of the function. Scope is something that will be covered in detail in a later chapter, but for now we can just observe that the **name** variable is defined inside the function, while **names** is defined outside of it.

It's easy to imagine how much tidier this is now that we don't have duplicate code, just multiple calls to the same function. This makes our code more readable, maintainable, and easier to debug. This process of restructuring our code is called refactoring. We should always aim to write code that's easy to maintain, debug, and extend, and having good structure plays a big part in this.

## Passing by Value, Passing by Reference

Function arguments are values that we pass into our function. If we think of our function as a discrete bit of functionality, then our parameters allow us to give it what it needs to run. There are two ways of passing parameters into functions, by value and by reference, and it's important to understand the difference.

When we pass an argument into a function by value, this means we're making a copy, and will be working with that. The easiest way to visualize this is by writing a small test application. Observe the following code:

```C++
// Pass by value-by-reference example.
#include <iostream>
#include <string>

void Modify(int a)
{
    a = a - 1;
}

int main()
{
    int a = 10;
    Modify(a);
    std::cout << a;
}
```

In this simple program, we define a number to be 10, pass it to a function that will subtract 1 from it, and then print that value. Since we started with 10 and are subtracting 1, it would be reasonable to expect the output to be 9. However, when we run the preceding snippet, we obtain the following output:

### Why Are We Outputting 10?

Because when we passed our **a** variable into our function, it was passed by value. The function made a local copy of **a**, in this case 10, and then anything it does to that value is completely separate from the original **a** value we passed in.

Passing by reference is the opposite of this and means, "Actually work on this variable; don't make a copy." Again, it's easiest to see this in action. Let's make the following amendment to our code:

`void Modify(int& a)`

A very subtle change, but what we've done here is added **&** after our **int** type in the function. This symbol means "the address of." We have chapters later in the course that will cover memory in much more detail, so we'll keep it light here, but in practical terms it means, "Don't make a copy; actually use that value."

Let's re-run the code with this change in place.

Passing by value or by reference is an important concept to understand. If you're working with big objects, passing by value can be expensive because temporary objects have to be constructed/deconstructed. This is another topic that will be covered in later chapters. For now, taking away the fact that values can be passed either by value or by reference (as we've seen here) is sufficient. We'll build on this later.

## Function Overloading

Writing functions to encapsulate our behaviors is a great step towards creating versatile and maintainable code. We can do more however; we can overload them. Overloading, in this context, means providing more than one version of the function. Let's say we define a simple function to multiply two numbers:

```C++
int Multiply(int a, int b)
{
    return a * b;
}
```

This function's arguments are of type **int**, so what happens if we wanted to multiply **float** types or **double**? In this case, they'd be converted to integers and we'd lose precision, not something we generally want. In order to solve this, we can provide another declaration of the function, with the same name, that can use those types. Our function declarations would look like this:

```C++
int Multiply(int a, int b);
float Multiply(float a, float b);
double Multiply(double a, double b);
```

What's great is we don't need to worry about calling the correct version of this function. Given we provide the correct types, the compiler will automatically call the appropriate function for us. We can see this in action with a simple test. We can create function definitions for each of these and add a unique output to each so we can tell which one's been hit.

Here is an example of how to do this:

```C++
// Function overloading example.
#include <iostream>
#include <string>

int Multiply(int a, int b)
{
    std::cout << "Called the int overload." << std::endl;
    return a * b;
}

float Multiply(float a, float b)
{
    std::cout << "Called the float overload." << std::endl;
    return a * b;
}

double Multiply(double a, double b)
{
    std::cout << "Called the double overload." << std::endl;
    return a * b;
}

int main()
{
    Multiply(3, 4);
    Multiply(4.f, 6.f);
    Multiply(5.0, 3.0);
    return 0;
}
```

In the preceding code, we have our overloaded function and three calls to it, each with a different type. When you run this application, the following output is obtained:

As we can see, the compiler knew which version of the function to call since we matched the specified parameter types in each case. A **multiply** function is a bit redundant, and certainly a simple use case of this, but demonstrates nicely how we can make our functions more useful and flexible.

Another way to achieve this flexibility is through templates. Instead of overloading a function for each individual type, with a template you create a single, highly generic version of the function that can accept any type. Templates will be covered in a later chapter.

## Default Parameters

Another way we can make our functions more flexible is with default parameters. This allows us to make some of our parameters optional, and we do so by giving them a default value in the declaration as follows:

```C++
return_type function_name(type parameter1, type parameter2 = default value);
```

This function could now be called in two ways:

`function_name(value1, value2);`

In this case, both parameter values are passed into the function as normal:

`function_name(value1);`

In this case, since the second parameter has been omitted, the default value will be used instead. Having the ability to provide default parameters allows us to make our functions more flexible in what they can do, but there's a limit to this. The point of a function is to neatly encapsulate a certain behavior, so we don't want to make it so flexible that it starts being responsible for multiple behaviors. In this case, it would be better to create a new discrete function.

Let's have a quick look at an example of this with another exercise.