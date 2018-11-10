---
layout: post
title: Using the `AGGREGATE` function
categories:
  - blog
notes:
  - //TODO provide usage details
  - //TODO show an image
---

# Using the `AGGREGATE` function

Pro Tip: use `AGGREGATE` when you want to ignore cells with errors or hidden cells.

The `AGGREGATE` function allows for performing statistical aggregations (hence the name) with more customization than the standard `MIN`, `MAX`, etc. functions. The `AGGREGATE` function is also odd in that it uses a set of magic numbers (or constants) as parameters for what aggregate to complete as well as any options that will be applied. Where the `AGGREGATE` function shines above the stocks functions is that it allows you to handle: cells with errors and hidden cells. With the power to consider those options comes the need to be very explicit about the calculation you want to use. For error handling, it can be quite frustrating to run an `AVERAGE` of 100k cells to find out that 2-3 of them have random errors of no consequence. You can specify the `ignore errors` option to have AGGREGATE disregard them. For hidden cells, you are most likely only going to use that in the context of filtering. You set some filters and then use `AGGREGATE` to only get the `SUM` of the visible cells. This allows you to specify any filters you want manually (as opposed to a `SUMIF` or an array formula) and then have a single formula which can give the aggregations you want.

For excluding hidden cells, there is not an alternative way to handle that without using VBA. For ignoring errors, the alternative is often an array formula, helper column, or possibly a `SUMIF` or other `IF` function.
