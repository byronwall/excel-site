---
layout: post
title: Use Data Validation as a dropdown
categories:
  - blog
notes:
  - // TODO add picture of results
---

# Use Data Validation as a dropdown

Pro Tip: use Data Validation to provide a user with a list of choices

One of the more common tasks when using Excel either as a database or a front end for analysis is limitnig the choices of the user. Sometimes this is done because you want to avoid errors. Other times, you can provide a list of choices based on the current state of the sparedsheet. One of hte most common tasks in this arena is to make it simpler for the user and avoid typing some value into a cell. Maybe you prpvide an interface to plot 1 of several columns. The easiest way to ask teh user for their choice is to type in teh header vale of the column to plot. You can use a dropdown to limit the user's optiojns to only those that are valid.

You can use the `Data->Data Validation` tools to provide a drop down of choices. In that menu, choose `List` as the source data. From tehre, you have two choices for how to define the list:

- Select a region of cells **on the current sheet**
- Provide the name of a Named Range

THe former option is easiest if you know the region fo cells will be a fixed size and is located on teh current sheet. There is no good reason that Excel limits you to the current sheet here, but realize it is a real limit. To get around it, you can use a Named Range.

For a Named Range, you will use this for 2 reasons:

- To get around the single sheet rule above
- To allow for a dynamically sized region based on the sheet state

Option 2 is quite prowerful because it means that you can provide the user with a list of choices that adapt to the current state of the sheet. This is great when the list of headers can chagne size. Or maybe you wnat to allow them to select any _unique_ value from a column. In either case, you can whip up a Named Range with all those good dynamic refernces (e.g. use `INDEX` somewhere). You can also use an array formula <sup>1</sup>.

<sup>1</sup> Note that Named Ranges will always evaluate as array formulas so you don't have to enter with `CTRL+SHIFT+ENTER` (nor can you).
