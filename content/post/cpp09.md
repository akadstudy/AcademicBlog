---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Exercise 2"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T21:04:56+02:00
lastmod: 2020-09-17T21:04:56+02:00
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

# Defining Values with Preprocessor Directives

In this exercise, we're going to build a small application that will give a test score a letter grade. We'll define score thresholds in macros and use them to assign grades:

1. We'll start by including our iostream and string headers, and defining our grade macros:

```C++
// Preprocessor directives activity.
#include <iostream>
#include <string>

#define GRADE_C_THRESHOLD 25
#define GRADE_B_THRESHOLD 50
#define GRADE_A_THRESHOLD 75
```

Define these thresholds as you see fit.

2. Allow the user of the program to input their test score by typing in the following code:

```C++
int main()
{
    int value = 0;
    
    std::cout << "Please enter test score (0 - 100): ";
    std:: cin >> value;
```

Don't worry that we've not yet covered the IO statements that we're about to use. We'll be covering them next.

3. Output the grade the user got based on their test score.

This is where we use the values we defined earlier. By defining these in macros, we can easily update them at a later date. This is nice as it allows us to modify the thresholds in a single location. Everywhere those macros are used will be updated as a result. Use the following code to do this:

```C++
if (value < GRADE_C_THRESHOLD)
    {
        std::cout << "Fail";
    }
else if (value < GRADE_B_THRESHOLD)
    {
        std::cout << "Pass: Grade C";
    }
else if (value < GRADE_A_THRESHOLD)
    {
        std::cout << "Pass: Grade B";
    }
else
    {
        std::cout << "Pass: Grade A";
    }
}
```

4. The complete code looks like this:

```C++
// Preprocessor directives activity.
#include <iostream>
#include <string>
#define GRADE_C_THRESHOLD 25
#define GRADE_B_THRESHOLD 50
#define GRADE_A_THRESHOLD 75

int main()
{
    int value = 0;
    std::cout << "Please enter test score (0 - 100): ";
    std::cin >> value;
    if (value < GRADE_C_THRESHOLD)
    {
        std::cout << "Fail";
    }
    else if (value < GRADE_B_THRESHOLD)
    {
        std::cout << "Pass: Grade C";
    }
    else if (value < GRADE_A_THRESHOLD)
    {
        std::cout << "Pass: Grade B";
    }
    else
    {
        std::cout << "Pass: Grade A";
    }
}
```

5. Now let's run our program. If a user inputs a score between 1-100, we can provide them with a letter grade. For an input of 50, you will obtain the following output: 