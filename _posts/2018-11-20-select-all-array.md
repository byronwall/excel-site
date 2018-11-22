---
layout: post
title: Find all cells in array formula
categories:
  - blog
notes:
  - // TODO add picture of results
---

# Find all cells in an array formula

Pro Tip: use `CTRL+/` to select all cells in an array formula.

Array formulas are great until you go to edit them. They have the nasty property that you must edit the entire region of the array formula. You are not able to edit a cell in the middle of the array. Nor are you able to delete or clear part of the formula. The fastest way to edit or delete an array formula then is to select the whole thing using `CTRL+/`. From there you can hit `F2` to edit the thing or delete to clear it out.

When editing array formulas, there are two other relevant tips:

- You can extend an array formula down further by dragging the corner like normal. You can not shrink the formula however.
- To shrink an array formula, you must first delete its current cells. Copy the formula before doing this to avoid losing it.
