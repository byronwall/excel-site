---
layout: post
title: Improving the speed of array formulas
categories:
  - blog
notes: -
---

# Improving the speed of array formulas

Pro Tip: never point an array formula to an entire column of cells. Create a named range using INDEX:INDEX instead of the column.

The single biggest performance hit for an array formula is processing an entire column of cells. This is an easy trap to fall into because for non-array formulas, the problem does not exist. For non-array formulas, Excel is optimized to only process the used range. You can accidentally ruin the used range, but at least you have to work to make them slow. Array formulas are the opposite, they are slow from the start if you process an entire column. It's typically the case that you will notice this speed issue once you've done it a couple of times or once you then copy that array formula through a column of cells. This can quickly give 10,000 slow calculational which accumulate rapidly on a recalculation.

If this approach is so slow, why does it happen? Well, you want to process the entire column of data but you don't know in advance how many cells will have data. The solution: using a dynamic named range instead of the column name. A dynamical named range is a range which involves at least one call to `INDEX`. Assuming you have some data in column B, the simplest version is

```txt
=B1:INDEX(B:B,COUNTA(B:B))
```

What did we just do? Create a new range that starts at `B1`. It then uses `COUNTA` to determine how many cells of data there are. That count is then used to grab the last cell in the column to end the range. If `COUNTA` returned `1089` then the range above equates to `B1:B1089`. `COUNTA` works well for data that does not have any blanks. There are more complicated ways to count cells if you have blanks or other issues. Even if your named range is a little big, you are often still OK. Remember, the goal was to use fewer than the 1 million cells that the array formula would use by default.
