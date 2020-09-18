---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "if/else"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-18T17:48:25+02:00
lastmod: 2020-09-18T17:48:25+02:00
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

# if/else

One of the most basic, yet most important, control flow statements is if. This simple keyword is at the heart of all logic, allowing us to perform a given action only if a specified condition is true. By chaining these **if** statements together in creative ways, we can model any logical system.

The syntax for an **if** statement is as follows:

`if (condition) { // do stuff. }`

If the statement we use as our condition resolves to **true**, then the code within the curly braces will be executed. If the statement is **false**, then it will be skipped. Our condition can be anything that can be either true or false. This can be something simple, such as checking the value of a Boolean, or something more complex, such as the result of another operation or function.

We also have the **else** statement. This allows code to be executed **if**, and only if, a preceding if statement's condition evaluates to **false**. If the condition evaluates to true, however, and the **if** statement is thereby executed, the code within the **else** statement will not be executed. Here's an example:

```C++
if (MyBool1)
    {
        // Do something.
    }
    else
    {
        // Do something else.
    }
```

In this example, if **MyBool1** was **true**, then we'd execute the **// Do something** code but not **// Do something else**. If **MyBool1** evaluated to **false**, however, we'd execute the **// Do something else** code but not **// Do something**.

An **else** statement can also be used together with an **if** statement. With an **else/if** block in place, should the first **if** check fail, then the second will be evaluated. Here is an example:

```C++
if (MyBool1)
    {
        // Do something.
    }
    else if (MyBool2)
    {
        // Do something else.
    }
```

In this example, **MyBool1** will be checked first. If that returns **true**, then the **// Do Something** code will be executed but **// Do something else** will not. If **MyBool1** was **false**, however, **MyBool2** would then be checked, and the same rules would apply: if **MyBool2** was true, then **// Do something else** would execute. So, if **MyBool1** and **MyBool2** were both false, then neither code would be executed.

It's also possible to place **if** statements inside one another. This practice is referred to as nesting. Here's an example:

```C++
 if (MyBool1)
    {
        if (MyBool2)
        {
            // Do something
        }
    }
```

In this example, if **MyBool1** returns **true**, then the second **if** statement will be evaluated. If **MyBool2** is also **true**, then **// Do Something** will be executed; otherwise, nothing will get executed. C++ allows us to nest many levels deep. The standard suggests 256 (although this isn't enforced), but the more levels deep you go, generally, the more confusing the code. It's good practice to minimize nesting where possible.

Now, let's get some code written and see these **if / else** statements in action.