---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Activity 1"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-18T10:10:03+02:00
lastmod: 2020-09-18T10:10:03+02:00
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

# Writing Your Own C++ Application

The aim of the activity is to write a system that will ask users for their first name and age. Users will be placed into groups based on their age, and we'll use macros to define these age brackets. We'll print the user's information back to them, along with their assigned group (the name of which is also at your discretion), using functions to encapsulate any repeated functionality. Our desired outcome will be a small program that will be able to sort users into groups, as shown in the following screenshot:

Before you begin, ensure that all previous exercises have been completed because this activity will test a number of the topics that we've covered in this introductory chapter. Here are the steps to complete the activity:

1. Define your age bracket thresholds using **#defines**.
2. Define a name for each group using **#defines**.
3. Output text asking the user for their name and capture the response in a variable.
4. Output text asking the user for their age and capture the response in a variable.
5. Write a function that will accept age as a parameter and return the appropriate group name.
6. Output the user's name and the group that they have been assigned to.