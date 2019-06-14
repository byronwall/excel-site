---
layout: post
title: Extracting text with LEFT, RIGHT, MID
categories:
  - blog
notes:
  - // TODO add picture of results
---

# Extracting text with mid left right and find

Pro Tip: use `LEFT`, `RIGHT` and `MID` to extract parts of your text.

Extracting a subset of text is a common task when working with text. It's so common that Excel provides 3 functions for the most common operations. The 3 functions allow you to extract text from the start, end or middle of a string. These functions are quite helpful when you have text that is fixed width. That is, when you have text which is structured the same across multiple cells. Social security numbers are a common example, but it could just as easily be a functional location from an SAP export.

```txt
=LEFT("text", 2)
=MID("text", 1, 2)
=RIGHT("text", 2)
```

Working with fixed width text makes it easy but oftentimes you will need to combine `FIND` with these functions. `FIND` works to search for text and returns the index where it occurs. This allows you to work with data that is of variable length. You can use similar tricks to determine how many characters to extract.

The string process functions are one area where you can get great milaeage from VBA helping you out. Very often, a tasks is trivial in VBA but difficult in Excel. A common example is splitting text based on a delimiter. It's a single function in VBA but a complicated set of formulas in Excel.
