---
layout: post
title: Using the `IFERROR` function
categories:
  - blog
---

# Using the `IFERROR` function

`IFERROR` provides a simple means of forcing any error values into a single default. It works well when you know that an error is possible leading to a bad result. It is effective when working with functions that do not handle errors well: `AVERAGE`, `MIN`, `MAX`, and the other statistical functions. The major downside of IFERROR is that it provides no indication that an error was the result, especially if your default value could have occurred naturally. This can make spot checking your work more difficult since it's not obvious an error occurred.
