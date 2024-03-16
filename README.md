# LLN-viz
Exploring the Law of Large Numbers
## Introduction
The Law of Large Numbers (LLN) states that as the sample size increases, the sample mean tends to converge towards the population mean. In this notebook, we will explore the application of LLN using a dataset containing the heights of men in Australia over a period of 120 years (1850-1970). We will collate the data, calculate the mean height for the entire period, and then sample a smaller period to compare the sample mean with the original mean. This analysis will help us understand how the sample mean relates to the population mean as the sample size increases.

#### A better dataset with population data from 1850 was found. It is contained in "pop_data.csv".
##### _Sources:_
- Australian Bureau of Statistics 2010, Australian Demographic Statistics, Sep 2009, Cat.no. 3101.0, Australian Bureau of Statistics, Canberra, viewed 25th March, 2010, <http://www.abs.gov.au>.
- Australian Bureau of Statistics 2008, Australian Historical Population Statistics, 2008, Cat.no. 3105.0.65.001, Australian Bureau of Statistics, Canberra, viewed 10th August, 2009, <http://www.abs.gov.au>.
- Australian Bureau of Statistics 2008, Australian Demographic Statistics, Dec 2008, Cat.no. 3101.0, Australian Bureau of Statistics, Canberra, viewed 10th August, 2009, <http://www.abs.gov.au>.
- http://chartsbin.com/view/eoo

- heights.csv has average height of men in Australia from 1850 to 1970 (120 years) among other countries. description: Average height of men by year of birth, 1810 to 1980. Link: https://ourworldindata.org/grapher/average-height-of-men-for-selected-countries?tab=table

  ## Sample Mean Comparison Function

The `sample_mean_comparison` function is designed to explore the Law of Large Numbers by comparing the mean and standard deviation of a randomly sampled subset of data with the actual values from the entire dataset.

### Function Parameters

- `number_of_years_to_be_sampled` (integer): Specifies the number of years to be randomly sampled from the dataset.

### Function Details

The `sample_mean_comparison` function performs the following steps:

1. Randomly selects a specified number of years from the `merged_data` dataset using the `sample()` function without replacement.
2. Subsets the `merged_data` dataset based on the sampled years using the `subset()` function.
3. Calculates the mean height and standard deviation of the sampled data using the `mean()` and `sd()` functions, respectively.
4. Creates a data frame `sample_vs_original` to compare the sample mean, actual mean height, sample standard deviation, and actual heights standard deviation.
5. Generates a line plot using `ggplot2` to visually compare the mean heights of the sampled data and the entire dataset over time.
   - The plot includes horizontal lines representing the sample mean and the actual mean height for easy comparison.
   - The plot has a minimalistic theme and sets the y-axis limits for better visibility.
6. Returns the `sample_vs_original` data frame containing the comparison results.

### Usage Example

To use the `sample_mean_comparison` function, simply call it with the desired number of years to be sampled:

```R
sample_mean_comparison(5)
```

This will randomly sample 5 years from the `merged_data` dataset, calculate the sample mean and standard deviation, create a comparison data frame, generate a line plot, and return the comparison results.

### Function Output

The `sample_mean_comparison` function returns a data frame `sample_vs_original` with the following columns:

- `Sample Mean`: The mean height calculated from the sampled data.
- `Actual Mean Height`: The actual mean height calculated from the entire dataset.
- `Sample Standard Deviation`: The standard deviation of heights calculated from the sampled data.
- `Actual Heights Standard Deviation`: The actual standard deviation of heights calculated from the entire dataset.

Additionally, the function generates a line plot that visually compares the mean heights of the sampled data and the entire dataset over time.

### Requirements

To use the `sample_mean_comparison` function, make sure you have the `ggplot2` package installed and loaded. You can install it by running `install.packages("ggplot2")` and load it with `library(ggplot2)`.

Also, ensure that you have set the appropriate plot width and height using `options(repr.plot.width = 12, repr.plot.height = 8)` before running the function.

---

