---
layout: post
title: Faster Array Formulas
categories:
  - blog
notes:
  - // TODO add picture of results
---

# Faster Array Formulas

Pro Tip: never refer to an entire column in an array formula

If you want to bring a good spreadsheet to a screaming halt, use an array formula that points to an entire column. Even better, copy that formula down a column or two and across a couple rows. Once you're done with that madness, copy the sheet 11 times and adjust the names to match months.

Arrays formulas are one of the fastest ways to have Excel crunch through data. Their only pitfall is that they choose to process the entire range they are given. They are not optimized in the same way that `SUM` is when you point to a whole column. With modern versions of Excel, this means that an array formula must process 1 million+ cells for every column you refer to.

The solution: find some way to decrease the size of the range. Several choices:

- If your data is fixed size, just refer to the data. Name a range if you're tired of dragging.
- If your data is dynamic, use a dynamically named range to generate the correct range. Might sound crazy but you can create 100+ named ranges and still have a crazy fast spreadsheet.
- Don't use an array formula. Tough pill to swallow sometimes, but a "good" and simple array formula can sometimes be worse than the nasty normal formula you're replacing.
- Kick your logic into a UDF... sky's the limit. Depending on how you swing that VBA stick, you can create UDFs that are faster than a full column reference in an array formula.
