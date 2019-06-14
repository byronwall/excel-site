---
layout: post
title: Removing duplicates
categories:
  - blog
notes:
  - // TODO add picture of results
  - // TODO better explanations of formulas?
---

# Removing duplicates

ProTip: use Excel's built in ability to remove duplicates whenever you need to clean up data.

Removing duplicates from data is a common task. Excel provides a range of options to remove duplicates from your data. You can combine those features with formulas and other tools to complete whatever processing you've got to do.

There are a handful of reasons to remove duplicates:

- Your data came from a noisy source with duplicates
- Your data has more information than you need (e.g. extra columns)
- You're using a formula to process raw data and want to filter through its results

To remove duplicates, select your data and go to the Data tab. From there is the `Remove Duplicates` button. It will open up to allow you to select the columns which should be considered in the `is it a duplicate? logic`. By default all of the columns will be selected which means that a given row will be deleted if all of its columns match all of the columns of another row. If you want to consider fewer columns (donw to a single one) you can start unchecking.
