---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Exercise 3"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T22:46:18+02:00
lastmod: 2020-09-17T22:46:18+02:00
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

# Reading User Details

In this exercise, we're going to write an application that will allow you to input your full name and age. We'll then print this information out, formatting it into complete sentences. Perform the following steps to complete the exercise:

1. Define the **firstName**, **lastName**, and **age** variables, which will hold our user's inputs, as shown in the following snippet:

```C++
// IO Exercise.
#include <iostream>
#include <string>

int main()
{  
  std::string firstName;
  std::string lastName;
  int age;
```

> **Note**: We're going to be covering data types in their own chapter later, so don't worry if the exact nature of these variable types isn't clear at this point.

2. Type in the following code, which will request the user to input their first name:

```C++
std::cout << "Please enter your first name(s): ";
getline(std::cin, firstName);
```

3. We'll do the same for surnames, again using **getline()** using the following snippet:

```C++
std::cout << "Please enter your surname: ";
getline(std::cin, lastName);
```

For our final input, we'll allow the users to input their age. For this, we can use **cin** directly because it's our last input, so we need not worry about terminating lines characters, and we're expecting a single numerical value.

4. Type the following code to have the user input their age:

```C++
std::cout << "Please enter your age: ";
std::cin >> age;
```

> **Note**: Again, it's only because we're writing simple example programs that we're trusting our users to input the correct data and not doing any validation. In a production environment, all user input data would be strictly validated before use.

5. Finally, we'll present this information back to the user, making use of chained insertions to format complete strings and sentences using the following code:

```C++
std::cout << std::endl;
std::cout << "Welcome " << firstName << " " << lastName << std::endl;
std::cout << "You are " << age << " years old." << std::endl;
```

6. The complete code looks like this:

```C++
// IO Exercise. 
#include <iostream> 
#include <string> 

int main() 
{ 
    std::string firstName; 
    std::string lastName; 
    int age; 
    std::cout << "Please enter your first name(s): "; 
    getline(std::cin, firstName); 
    std::cout << "Please enter your surname: "; 
    getline(std::cin, lastName); 
    std::cout << "Please enter your age: "; 
    std::cin >> age; 
    std::cout << std::endl; 
    std::cout << "Welcome " << firstName << " " << lastName << std::endl; 
    std::cout << "You are " << age << " years old." << std::endl; 
} 
```

7. Run our application now and test it with some data.
  
Thus, with the completion of this exercise, we have put together, through basic IO, a little program that allows users to register their details against something. We will now move on the next topic—functions.