---
layout: post
title: Using ROW() to create a counter
categories:
  - blog
notes:
  - // TODO add picture of results
  - // TODO better explanations of formulas?
---

# Using `ROW()` to create a counter

Pro Tip: use the `ROW` formula when you need a counter, access to the current row, or the row of a reference cell.

The ROW function can be quite handy when you are in need of information about the current cell or a reference cell. It gives you the row of a cell as a number. If you are working with `INDEX` formulas much, ROW becomes an essential tool to get references to cells to feed back into INDEX. You can use the same sort of tricks to obtain the ROW of a reference cell. That row can then be used to INDEX into another reference. This becomes particularly useful when you are working with some sort of offset to a given cell since those offsets are much harder to deal with with normal references.

Another fun use of ROW is when you simply need a counter. It's easy enough to create a helper column with a simple `=CELL_ABOVE+1` but if you want to spare a column, you can also just use ROW. If you need the counter to start at some spot, you can do `ROW()-ROW(REF_CELL)`.

If you are thinking, why would I need a counter, check out the article about using MOD. You may also find that a counter is a good starting point for grouping blocks of cells. See also the moving average article for an example of using ROW.
