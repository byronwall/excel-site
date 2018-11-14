---
layout: post
title: Dealing with text as number errors
categories:
  - blog
notes:
  - //TODO add picture of green array
  - // TODO add formatting for formulas
---

# Dealing with text as number errors

Pro Tip: be careful using lookup functions that contain a mix of TEXT and NUMBERS, especially if the data was pasted from somewhere else.

Ever have a lookup function (e.g. INDEX, MATCH, VLOOKUP) that you swore was correct but which refused to return the right value? Even worse you can scroll to the exact spot that should be matching? Then you scroll back up and see that green arrow which says `"Number stored as text"`? It's quite possible you were fighting Excel's handling of text and numbers.

Excel has a fairly strict rule which says that comparing a number (e.g. `7`) and text (e.g `cats`) will always return `FALSE`. Excel also allows you to store a number (e.g. `7`) as text (e.g. `7`). With default formatting in place, Excel then tries to provide a visual that one is text and the other is a number by right and left aligning them. When you are interacting with Excel "normally", it is quite difficult to accidentally enter a number as text. You typically have to manually set the cell type to `Text` and then type the number in. It's very easy however to paste something from the internet that Excel misinterprets. Even easier is using the output of an SAP export directly. Either way, it's possible to end up with a cell that contain text but looks like a number. This wreaks havoc on your lookups though because Excel is using equality to determine which cells to return. Since a number can never be equal to text, this guarantees you won't consistently get the result you want.

Ways to diagnose this problem:

- Use the friendly warning from Excel about `Number stored as text`
- Use the `ISNUMBER` or `ISTEXT` function to check what type a cell is
- Test a cell against some other value using the `=` comparison

Ways to deal with this issue for formulas:

- Use the friendly warning from Excel to convert the †ext to number (warning this can be slow)
- Use a formula to force the value to knowingly be text (using `TEXT`) or a number (using `VALUE`)
- Use VBA to force the cell's value to be stored as a number or text

Ways to not solve this problem:

- Wish that Excel were less stringent about comparisons between numbers and text.
