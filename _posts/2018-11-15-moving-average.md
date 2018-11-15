---
layout: post
title: Creating a moving average using INDEX:INDEX
categories:
  - blog
notes:
  - // TODO add picture of results
  - // TODO better explanations of formulas?
---

# Creating a moving average using `INDEX:INDEX`

Pro Tip: Use `AVERAGE(INDEX:INDEX)` to create a moving average of data that is centered and works for data of any size.

Moving averages are one of the bed rock techniques of processing data. They are useful for removing noise, determining a seasonal average, and generally cleaning up data. The downside of moving averages in Excel is that you generally end up making a new set of formulas every time. The problem comes down to the `window` that is used for a moving average. A window is the number of data points to include in the average. For a moving average, you can either have a window that looks backwards or that is centered and includes data before and after the current point. If you work with real time data, you can only have centered moving averages by delaying the calculation. On the flipside, for data that is alreayd collected, you will introduce a phase shift with a non-centered moving average. That phase shift will be dependent on the window of the data.

For these reasons, I always use a centered moving average when working with non-real time data. This makes it possible to change the window size without worrying about shifitng data relative to other data.

So, how do we actually make the average? The easiest approach is to use `AVERAGE(RANGE)` where `RANGE` is centered on the current point and includes `N` cells on either side. For example, you want a window of 3 and the current point is at `B5`, you will do `AVERAGE(B2:B8)`. If you use relative references (no dollar signs), you can copy that formula down through your data. The downside of this approach is multi-fold:

- At the ends of the data, you will get bad results. At the top, you are likely to go out the top of the spreadsheet and get `#REF!` errors. At the bottom, you will include blank cells and get values that are too small.
- If you want to change the window size, you need to edit all the formulas, define a new range, and then fill the formula.
- If your data contains any errors, you will get errors in your average.

For the final issue, use `AGGREGATE`.

For the first 2 issues, you need to decide how to handle the problem. The biggest decision is how often you want to change the widnow or how often teh size of the data changes. If you want to cahnge the window or hte data size, you will need ot use dynamic ranges. A dynamic range is one where your provide the parmaeters to the range as inouts instead of selectiojn the range szie ahead of time.

To make the dyanmic range, you will use a combination of `INDEX` and `ROW`. `INDEX` allows you to create a reference using dynamic inputs. `ROW` gives you information about the spreadhseet allowing you to define the index.

The answer, assuming data is in column named `DATA`

```txt
=AVERAGE(INDEX(DATA,ROW()-20):INDEX(DATA,ROW()+20))
```

That formula allows you to use `20` as the window size. You could easily mkae that a named range also, or a refernece to a cell that you can change. That formulas works create for the window size, but it still has problems at the end. To handle those, you need to prevent the range from leaving the data in teh column. You also don't want to make the range go out the top of oyur data. Assuming you data has a header, the best version is then:

```txt
=AVERAGE(INDEX(DATA,MAX(ROW()-20,2)):INDEX(DATA,MIN(ROW()+20,COUNTA(DATA))))
```

The extra calculations there prevent the row from being less than `2` or greater than the size of the data.

The final option is to throw in an `AGGREGATE` or an `IFERROR` if you don't want to propagate errors.
