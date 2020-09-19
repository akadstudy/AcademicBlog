---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Exercise 6"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-18T18:25:42+02:00
lastmod: 2020-09-18T18:25:42+02:00
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

# Ternary Operator

The ternary operator is a neat feature that allows us to quickly assign a value based on the outcome of an **if** statement. This is best shown with an example. Perhaps we have a float variable, the value of which depends on a Boolean. Without using the ternary operator, we could write this as follows:

```C++
if (MyBool == true)
    {
        MyFloat = 10.f;
    }
   else
    {
        MyFloat = 5.f;
    }
```

> **Note**: Here, we've used **==** instead of just **=.** The **=** operator assigns a value to a variable, whereas the == operator checks whether two values are equal, returning true if they are, and false otherwise. This will be covered in more detail in a later chapter on operators.

Using the ternary operator, we could also write this same code as follows:

`MyFloat = MyBool ? 10.f : 5.f;`

That's much more concise. Let's break down the syntax here and see what's happening. A ternary statement is written as follows:

`variable = condition ? value_if_true : value_if_false;`

> **Note**: While ternary statements can be nested as we saw earlier with **if** statements, it's probably best to avoid it. They can be a real pain to read and understand at a glance.

We start by specifying the condition that we want to evaluate and follow it with the **?** character. This sets our ternary statement in motion. We then define the different values we want to use if the value is **true** or **false**. We always start with the **true** value, followed by the **false** value, with them separated by the **:** character. This is a great way to concisely handle an **if/else** scenario.

## Exercise 6: Creating a Simple Menu Program Using an if/else Statement

In this exercise, we're going to write a simple program that provides menu options for a food outlet. Users will be able to select multiple options from a menu, and we will present the price information based on that choice.

Here are the steps to complete the exercise:

1. Create the template application, and output our three menu options to the user:

```C++
// if/else exercise – Menu Program
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
    std::cout << "Menu\n";
    std::cout << "1: Fries\n";
    std::cout << "2: Burger\n";
    std::cout << "3: Shake\n";
```

2. Next, we'll ask them to input their choice and store it:

```C++
 std::cout << "Please enter a number 1-3 to view an item price: ";
    getline (std::cin, input);
    number = std::stoi(input);
```

3. Now, we can use our **if/else** statements to check the user input and output the correct information:

```C++
if (number == 1)
    {
        std::cout << "Fries: $0.99\n";
    }
    else if (number == 2)
    {
        std::cout << "Burger: $1.25\n";
    }
    else if (number == 3)
    {
        std::cout << "Shake: $1.50\n";
    }
    else
    {  
        std::cout << "Invalid choice.";
    }

    return 0;
}
```

4. The complete code looks like this:

// if/else exercise – Menu Program
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
    
    std::cout << "Menu\n";
    std::cout << "1: Fries\n";
    std::cout << "2: Burger\n";
    std::cout << "3: Shake\n";
    std::cout << "Please enter a number 1-3 to view an item price: ";
    getline(std::cin, input);
    number = std::stoi(input);
    if (number == 1)
    {
        std::cout << "Fries: $0.99\n";
    }
    else if (number == 2)
    {
        std::cout << "Burger: $1.25\n";
    }
    else if (number == 3)
    {
        std::cout << "Shake: $1.50\n";
    }
    else
    {
        std::cout << "Invalid choice.";
    }

    return 0;
}

5. Run the application. When we input our menu option, we're presented with the correct information for that item, as shown in the following screenshot:

This ability to perform an action if a given condition is true really is at the heart of all programming. If you break down any system far enough, it will comprise "if x is true, do y." With this covered, the possibilities are endless.