---
layout: post
title: CONCATENATE and &
categories:
  - blog
notes:
  - // TODO add picture of results
  - // TODO add a link to bUTL
  - // TODO spelling
---

# Concatenation vs the & symbol

Toss Up: `CONCATENATE` and `&` both provide a simple means to join strings.

Excel provides two mechanisms for joining items together as a string: `CONCATENATE` and `&`. THat is, as something which will return `TRUE` from `ISTEXT`. They work the same but one works as an operator whereas `CONCATENATE` is a function. I've never had a preference for one over the other. Sometimes I get tired of holding shift and prefer using commas. Other times, I prefer the shorter function and use `&`.

When working with strings, the biggest issue is usually formatting. This is one of the more tedious aspects of strings. You often have to format all of your results using `TEXT` to prevent showing 99 decimal places. This is also usually required for returning dates in a string.

```txt
=CONCATENATE(A1,B2,C2)
=A1 & B2 & C2
```

The other major issue with strings is wanting to join together a range of cells into a single string. Excel provides no simple way to do this that takes the range as an argument. To do this, you will need to use VBA and a UDF which can join together the items. My bUTL addin has a couple of functions to help with that.
