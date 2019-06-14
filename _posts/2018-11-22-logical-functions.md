---
layout: post
title: Logical Functions
categories:
  - blog
notes:
  - // TODO add picture of results
---

# Logical functions

Pro Tip: get comfortable using `BOOLEAN` results in formulas. You can go a long distance in a complicated spreadsheet using simple booleans for control.

One of the simplest ways to make a spreadsheet complex is to start adding some logic with simple logic formulas. The logic functions do some evaluation and return a `BOOLEAN` value, `TRUE` or `FALSE`. Sometimes the result is useful but typically you will then feed that result into `IF` to get a different result depending on the previous result. One thing that is not always obvious to people is that you can have Excel work with boolean values directly. An example:

```txt
=IF(A1>1, TRUE, FALSE)
...even worse
=IF(A1>1, 1, 0)
```

I've seen that type of formula countless times. The user wants to keep track of some state based on logical functions but uses `IF` to return the values. The simpler version of above would be:

```txt
=A1>1
```

It looks a little odd at first but Excel will interpret that formula as wanting to return a boolean value. Your cell will then contain `TRUE` or `FALSE`. Depending on what you want to do with the result, you can use the boolena directly or with modification. The boolena can be used directly in an `IF` in a different cell. You can also use them for math; Excel typically treats `FALSE` as `0` and `TRUE` as `1`.

The most useful logic functions I use:

- Equality operator: `=`
- Inequality operators: `<` `>` `<=` `>=`
- The `IS` functions: `ISTEXT`, `ISNUMBER`, `ISERROR`
- Contains: `NOT(ISERROR(MATCH()))`

Extra details:

- `ISERR` and `ISERROR` are the same except for how they handle `#N/A!`. I never use `ISERR` since I want `#N/A!` to be called an error.
- `IF` will return `TRUE` or `FALSE` if you are missing the arguments. That is, `IF(SOME_CONDITION,,)` or `IF(SOME_CONDITION)` will return `TRUE` or `FALSE`. Of course at that point, you should just drop the if. Sometimes this is useful if want a default value for one or the other.
