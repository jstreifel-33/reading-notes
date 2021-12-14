# Intro to Pandas

[Source: 10 minutes to pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)

## Object Creation

`pd.Series(values)` can be used to create a series with default integer index.

`pd.DataFrame` can be used to organize tabular data.

## Viewing Data

`df.head` and `df.tail` can be used to view the beginning and end of tabular data, respectively

`df.index` will return the indexes of each row, `df.columns` will return the column headings.

`df.describe()` will show a quick statistic summary of data.

## Selection of data

Data can be selected **by label** using `df.loc[label]` or `df.at[label]`

Data can be secelcted **by location** using `df.iloc[loc]` or `df.iat[loc]`

## Etc.

There is a lot more that can be accomplished with Pandas, and really it would be better to refer to the documentation at the source for this reading.

### Comparisons and Gotchas

If an exception is encountered when performing an operation, refer to [comparisons](https://pandas.pydata.org/pandas-docs/stable/user_guide/basics.html#basics-compare) and [gotchas](https://pandas.pydata.org/pandas-docs/stable/user_guide/gotchas.html#gotchas) for possible guidance.