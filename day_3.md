# Advanced Pandas & Visualization

# Objectives
Students will be able to
- reshape dataframes via pivot tables, groupby, stack and unstack as necessary
- run timeseries analysis using timestamps, grouping, and periods
- create basic plots directly from the dataframe
- create more compelling visualizations with either plotly or seaborne

# Agenda
0. Pandas Warm-up and Review (45m)
1. Reshaping DataFrames (60m)
2. Working with Text Data (30m)
3. Practice on a New Dataset (60m)
4. Intro to Timestamps (45m)
5. Intro to Visualization within `pandas` (45m)
6. Intro to Visualization with Plot.ly (90)

# Pandas warm up and review
Read in [this dataset](https://s3.amazonaws.com/python-level-2/sales-funnel.csv) and answer the following:

0. What is this dataset?
1. What insights do you want to extract from it?

Then write code to answer the following:
0. How many rows have a price greater than $8,000?
1. How many rows are pending AND have a price greater than $8,000?
2. How many rows are pending OR have a price greater than $8,000?
3. Create an amount column that's equal to price * quantity. What's the total amount won?
4. What's the total amount won within the CPU product category?

# Reshaping dataframes
## Pivot tables
0. Let's Google `pandas pivot_table` and look at the docs.
1. What's a pivot table for?
2. Let's play around with the pivot_table function call and see what it does.

Creative exercise: pair up and come up with pivot tables you would find useful. Then we'll share.

## Groupby
0. Let's Google `pandas groupby` and look at the docs and a few examples.
1. How is this different from `pivot_table`?
2. Let's use it for some actual computations.

Using `groupby`, answer the following:

## Stack/Unstack
0. Let's Google `pandas stack unstack` and look at the docs and a few examples.
1. How does this relate to pivot tables?
2. What are indexes, single-level vs. multi-level?
3. Let's use it.

Using any combo of `stack`, `unstack`, `pivot_table` and `groupby`, answer the following:

# Working with Text Data
0. Let's go to the `pandas` docs section on working with text data.
1. Let's use `.str...` to select the rows that contain either pending or won.
2. Let's lowercase the Rep column with `.str.lower`

Exercises:
0. Replace the product category `CPU` with `monkey`
1. Upper case the product category column.
2. Create a new column called "contains_monkey" using `str.contains` based on the product category value.

# Practice on new dataset
## Solo
0. Read in [this dataset](https://raw.githubusercontent.com/suneel0101/lesson-plan/master/crunchbase_monthly_export.csv). What is it?
1. What is the max funding total? (Hint: may have to clean/convert that column; check dtypes)
2. Rename the columns so they're reasonable.
3. Create a pivot table of market against total funding, sorted from highest to lowest and only include the top 10.
4. How many companies contain the Game category?
5. What is the average funding total of companies from the city `New York`? How about `San Francisco`? How do they compare?
6. Get descriptive statistics on the dataset (good to do this at the beginning).

## Guided
0. What are the most popular categories? (intro to `str.get_dummies`)

# Intro to Timestamps
Read in [this dataset](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/citibike-data-truncated.csv). What is it ?

0. Let's delete the `Unnamed: 0 column`
1. Let's google `pandas timestamps`
2. Let's convert necessary columns into timestamps.
3. Let's compute the duration and add a column with the result.
4. Let's create a column called "5 minute periods".

## With Partner
0. What is the average trip time? What is the minimum and maximum trip time? What is the standard deviation?
1. What's average trip time broken down by station? Sort from longest to shortest, including only the top 15.
2. Create a column called `10 minute periods` that assigns the starttime to a ten-minute period.
3. Create a column called `month` that contains the month of the starttime

# Intro to Visualization within `pandas`
Let's go back to our crunchbase data.

0. Plot bar graph top 5 markets against funding total.
1. Plot pie chart of top 5 markets against funding total
2. Make the graphs nicer with axis labeling, tickmarks, title, etc.

## With Partner
Creative exercise: what over visualizations on this dataset would interest you? Create them! Then we'll share.

# Intro to Visualization with Plot.ly
We'll be sticking with our Crunchbase dataset for this section.

0. Let's google Plotly
1. Explore their charts gallery
2. Plotly vs d3?

## Installation
In your terminal, run `conda pip install plotly`

Let's make sure we have the right version:
```python
from plotly import __version__
from plotly.offline import download_plotlyjs, init_notebook_mode, iplot

print __version__ # requires version >= 1.9.0
```

Then let's initialize the offline mode:
```python
# run at the start of every ipython notebook to use plotly.offline
# this injects the plotly.js source files into the notebook
init_notebook_mode()
```

Our first plot:
```python
iplot([{"x": [1, 2, 3], "y": [3, 1, 6]}])
```

## The Documentation
[https://plot.ly/python/reference/](https://plot.ly/python/reference/)

## Basic Bar Charts
[https://plot.ly/python/bar-charts/](https://plot.ly/python/bar-charts/)

Let's create a dummy bar chart to learn how to use the plot.ly library.

### Solo Exercise
Re-do the earlier bar chart with Plot.ly.

## Grouped Bar Charts
<img alt="Grouped Bar Chart" src="https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/grouped-bar" width="300">

### Solo Exercise
What are the top 3 markets by funding total?

### Together
Let's use this to create a grouped bar side-by-side comparison of how many $$ were funding in NYC in each market vs SF. Instead of LA Zoo and SF Zoo, it'll be NYC and SF. Instead of giraffes, orangutans, and monkeys, it'll be the A, B and C markets.

## Stacked Bar Charts
<img alt="Stacked Bar Chart" src="https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/stacked-bar" width="300">

0. Let's turn the previous chart into a stacked one.
1. Let's change the colors.

## Timeseries Chart
<img alt="Timeseries" src="https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/timeseries" width="300">

[Here's](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/aapl.csv) the data on AAPL.

### Solo Exercise
Read it in with `pandas`.

### Together
Let's graph closing price over time.

### With Partner
Read in [GOOG data](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/goog.csv) and have both AAPL and Google plots on the same graph.

## Last stop: Datetime Heatmap
![Hotdog Eaters](http://i.huffpost.com/gen/3141626/images/n-ERIC-BOOKER-HOTDOG-large570.jpg)

[Here's](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/hotdog-eaters.csv) the data. Read it in with `pandas`.

This is a dataset of number of hotdogs eaten per day by these champion hot-dog eaters.

![Heatmap Example](http://i.imgur.com/y6maNWG.png)

We're going to walk through it together.
