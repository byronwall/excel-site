---
layout: post
title: Copy a worksheet to update its formulas
categories:
  - blog
notes:
  - // TODO add picture of results
---

# Using extra worksheets to get updated formula references that won’t copy well

Pro Tip: copy an entire worksheet and extract a difficult formula instead of trying to copy it.

You've got a very nice spreadsheet with some pretty nasty formulas. They are contained within a column of data but go here there and everywhere else in between. You know that if you just copy the formulas, they will re-reference and breka themsleves. You also know that they are not using dollar sign references correctly... since you never expected to copy them. The solution:

1. Copy the worksheet.
2. Insert a column to move the formulas where you want them.
3. Insert a column on the original sheet - you need the structure of the sheets to match
4. Copy/paste the entire column on the new sheet back to the old sheet
5. Voila

This trick works because Excel will not update references when copying cells across worksheets. This means you will get the formuals exactly as before without having to go add dollar signs everywhere.

There is some version of this trick that works for nearly all formulas copy/paste issues. The trick is usually thinking through how the re-reference will happen to work out the best steps. Sometimes, it's not possible to get dollar signs that do everything exactly right. This tool should always be in your box.
