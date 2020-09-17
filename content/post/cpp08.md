---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Preprocessor Directives"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-09-17T20:26:28+02:00
lastmod: 2020-09-17T20:26:28+02:00
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

# Preprocessor Directives

We've come across this term a few times now, so let's look at what it means. A preprocessor directive is a statement that runs before our code is compiled. This is incredibly useful for a range of different things, from header files to selective code compilation.

## Include

One of the most common directives, **#include**, we've already looked at; it means "*copy here.*" When the preprocess runs, it will literally copy and paste the contents of the included file in its place. This means that any functions, variables, classes, and so on defined in that header are now also accessible by the class containing the **include** directive.

There are two variations you'll see with this directive:

```C++
// Include example.
// Version 1 - Generally for system files.
#include <headerfile>

// Version 2 - Generally for programmer files.
#include "headerfile"
```

In **Version 1**, you're directing the preprocessor to look for the file using pre-defined search paths. This is typically used for system headers, and these paths might be set by your IDE, for example; they're implementation-defined.