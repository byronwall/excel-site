---
layout: post
title: Using the `AGGREGATE` function
categories:
  - blog
notes:
  - //finish
---

# Dangers within a filtered list

Pro Tip: use extra caution making edits inside filtered lists, especially pasting. Look for blue text on the left row numbers to see if filters are active.

Filters in Excel are the life blood of exploring larger data sets. The downside of filtered lists is that most of the time, some subset of your data will be hidden. This makes it easy to make a mistake that goes unnoticed for some time. When you're working inside filtered lists, you need to remember which operations will ignore hidden cells and which won't.

Ignore hidden cells (very difficult to ruin hidden data)

- Filling formulas down (`CTRL+D`)
- AGGREGATE functions with the correct option
- Statistical functions in the status bar (?)

Include hidden cells (very easy to ruin data or make a mistake):

- Pasting data (especially discontinuous ranges)
- Statistical functions in the Workbook

Pasting data is one of the worst limitations of filtered ranges because very often you would like to copy from your filtered source data and then paste directly over that filtered data. Essentially, you want to offset the current selection and paste 1:1. Unfortunately you need VBA to do that directly.

The easiest way around the limitations of filtered ranges is to sort your data so that are visible ranges are together. This prevents hidden rows being between the visible rows.
