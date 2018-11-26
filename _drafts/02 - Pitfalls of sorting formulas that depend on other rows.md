# Pitfalls of sorting formulas that depend on other rows

Pro Tip: be very careful when sorting data that contains formulas that refer to other rows

Excel has two great features which can combine to burn you: sorting large data sets and formulas that can point anywhere. If you have formulas that refer to other rows of data, you need to be very careful when sorting the data. The rule for Excel is: don't touch formulas when sorting. This means taht you can quickly ruin a sheet of formulas if you sort them. It's not uncommon during data analysis ot use a cell from a different row as a part of your logic. Maybe you have a time series of data and want to grab a data point 10 rows as a snapshot of the past. There are other ways of doing this, but the ismplest is to just click 10 rows up. If you then sort the data by some other field, you will find that the formulas do not still point 10 rows up. They will point to the same cells as before.
