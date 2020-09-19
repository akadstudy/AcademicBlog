---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Exercise 5"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-18T17:58:29+02:00
lastmod: 2020-09-18T17:58:29+02:00
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

# Implementing if/else Statements

In this exercise, we will write a simple application that will output a certain string based on an input value. The user will input a number, and the application will use **if/else** statements to determine whether it's either above or below 10.

Follows these steps to complete the exercise:

1. Enter the **main()** function and then define a variable called **number**:

```C++
// if/else example 1.
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
```

2. Write code that prints the **Please enter a number**: string, gets the user input, and then assigns it to the **number** variable:

```C++
std::cout << "Please enter a number: ";
    getline (std::cin, input);
    number = std::stoi(input);
```

> **Note**: We've used the **std::stoi** function here, which we first saw in *Chapter 1, Your First C++ Application*. This function converts a string value into its integer equivalent. For example, the string **1** would be returned as **int 1**. Combining it with **getline**, as we did previously, is a good way to parse integer inputs.

3. Use **if/else** statements to evaluate the condition based on the user input and then print either **The number you've entered was less than 10!** or **The number you've entered was greater than 10!**:

```C++
if (number < 10)
    {
        std::cout << "The number you entered was less than 10!\n";
    }
    else if (number > 10)
    {
        std::cout << "The number you entered was greater than 10!\n";
    }
    return 0;
}
```

4. The complete code looks like this:

```C++
// if/else example 1.
#include <iostream>
#include <string>

int main()
{
    std::string input;
    int number;
    std::cout << "Please enter a number: ";
    getline(std::cin, input);
    number = std::stoi(input);
    if (number < 10)
    {
        std::cout << "The number you entered was less than 10!\n";
    }
    else if (number > 10)
    {
        std::cout << "The number you entered was greater than 10!\n";
    }
    
    return 0;
}
```

5. Run the complete code in your editor. You will see that it evaluates the statements and outputs the correct string, as shown in the following screenshot

In this preceding exercise, we used two **if** statements that both evaluate a condition, but what if we want a default action if neither condition is true? We can achieve this by using an else statement on its own:

```C++
if (condition1)
    {
        // Do stuff.
    }
    else if (condition2)
    {
        // Do different stuff.
    }
    else
    {
        // Do default stuff.
    }
```

In this case, if neither **condition1** nor **condition2** proves to be true, then the code in the **else** block will be executed as a default. This is because there's no **if** statement, so nothing has to be **true** to enter it.

Applying this to our simple number example, we currently check whether the number is less than or greater than 10, but not if it's exactly 10. We could handle this with an **else** statement, as follows:

```C++
if (number < 10)
    {
        std::cout << "The number you entered was less than 10!\n";
    }
    else if (number > 10)
    {
        std::cout << "The number you entered was greater than 10!\n";
    }
    else
    {
        std::cout << "The number you entered was exactly 10!\n";
    }
```