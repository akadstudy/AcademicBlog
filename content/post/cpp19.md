---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "switch/case"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-18T19:48:08+02:00
lastmod: 2020-09-18T19:48:08+02:00
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

# switch/case

As we've seen, we can use **if/else** to perform certain actions based on which conditions are true. This is great when you're evaluating multiple conditional statements to determine flow, such as the following:

```C++
 if (checkThisCondition)
    {
        // Do something ...
    }
    else if (checkAnotherCondition)
    {
        // Do something else ...
    }
    ```

When we're evaluating the different possibilities of a single variable, however, we have a different statement available to us: the **switch** statement. This allows us to branch in a similar way to an **if/else** statement, but each branch is based on a different possible value of a single variable that we're switching on.

A good example of where this would be suitable is the menu application we created in the previous exercise. Currently, we chain **if/else** statements to handle the different possible values, but since we're switching on a single variable (the menu index), it would be more suitable as a switch statement.

A basic implementation of a **switch** statement block is as follows:

```C++
switch (condition)
    {
        case value1:
            // Do stuff.
        break;
	case value2:
            // Do stuff.
        break;
        default:
            // Do stuff.
        break;
    }
```

Applying this to the previous menu example, the condition would be the selected menu index that we read from our user, and the different values would be our supported possibilities (1-3). The default statement would then catch the cases where the user inputs an option that we're not handling. We could print an error message in those cases and have them select a different option.

A switch statement comprises a number of keywords:

- **switch**: This denotes the condition that we're evaluating. We're going to switch our behavior based on its value.
- **case**: Each case statement is followed by the value that we want to handle. We can then define our behavior for that scenario.
- **break**: This statement signals the end of our code for that given case. More on these in the next topic.
- **default**: This is the default case and is what will get called should none of the other cases match.

> **Note**: A default case is not required but is recommended. It allows us to handle all other values, perhaps throwing an exception.

An important limitation of **switch** statements is that they can only be used with certain types. These are whole numbers and **enum** values. This means that, for example, we couldn't use either string or float types within a switch statement.

> **Note**: Enumerated type, or **enum**, is a user-generated data type in C++. A detailed discussion on this is beyond the scope of this course. However, you can refer to the documentation for further details.

It's also worth noting that not every case needs a **break** statement. They are optional, though will likely be required in the vast majority of cases. If the **break** statement is omitted, however, then the flow of execution will continue to the next **case** statement until a break is hit. Be careful here because missing **break** statements is a common cause of hard-to-find bugs; ensuring each case has a **break** statement where needed could save you lots of potential debugging time down the line.

Perhaps the best way to see the use of a **switch** statement is to convert some **if/else** chains to switch statements. This will be the objective of the following exercise.