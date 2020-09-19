---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Refactor an if/else Chain into switch/case"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-18T20:56:49+02:00
lastmod: 2020-09-18T20:56:49+02:00
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

# Refactor an if/else Chain into switch/case

In this exercise, we will reuse the code from the previous exercise and refactor it into a **switch** statement. This will clearly show how we can represent the same functionality using either method. Since we're only checking the different possible values of a single variable, however, a **switch** statement is preferred.

We will break this down into a number of simple steps:

First, the variable we're checking here is **number**, so that's going to be the condition that we're switching on. Add that to a **switch** statement and open our curly brackets ready for the rest of the switch block:

```C++
switch (number)
    {
```