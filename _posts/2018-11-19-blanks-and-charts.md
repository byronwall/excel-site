---
layout: post
title: Blanks and Charts
categories:
  - blog
notes:
  - // TODO add picture of results
  - // TODO better explanations of formulas?
  - // TODO spell check
---

# Blanks and Charts

Pro Tip: use `#N/A!` to tell Excel to not plot a blank cell in a chart. All other options will plot a `0` instead.

When you're doing data analysis, one of the prime techniques for knowing what you've got is to chart the data. When you're charting, it's important to know how Excel will handle the variou sorts of good and bad data you give it. For charts, blank cells are one of the biggest hurdles. The mian rules for balnks cells and charts are:

- A blank cell will plot as a zero by default
- A cell is considered blank whether it is actually blank or is the result of a formulas which returns `""`.
- A cell with an error will plot as a zero unless...
- A cell with a `#N/A!` error will be skipped.

That means, if you are looking to force certain cells to not plot, you should find some way to return `#N/A!` as the value. If you want the cell to plot as a zero (why would you?), return anything else that looks like a blank cell.
