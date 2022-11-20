# Market Research on Restaurants in Los Angeles

View the notebook here using nbviewer.
View the presentation here.

## In this folder

| File name | Description |
| --- | --- |
|rest_data_us.csv         | Data on food establishments in Los Angeles |
|cafe_market_research.ipynb         | Analysis of trends in eateries in Los Angeles. |
|cafe_market_research-presentation.pdf           | PDF version of the final pptx presentation of summarized findings |

## Project Description

### Objective
We are looking to open a small robot-run cafe in Los Angeles. While the concept is very promising, this market research is intended to understand how the business will fit within the current market conditions once the novelty of robotic service wears off.
The term "eatery" is used to describe all the businesses in this dataset instead of "restaurant" as the latter is employed to describe one "type".

### Libraries to run the notebook locally
<b> *Python version 3.8.8* </b>
|Library| Version|
| --- | --- |
|pandas|1.3.1|
|numpy|1.19.2|
|seaborn| 0.11.2|
|matplotlib| 3.3.2 |
|plotly| 5.11.0|
|string| NA |
|usaddress| NA |
|json| NA |
  
## Project Overview

### Data processing
*(Suspected) Errors* 
- Replaced eateries with one seat to Null for the <code>num_seats</code> column.
- Bakeries with one location were changed to False for the <code>chain</code> column.
- Eateries for which there was a discrepency between the <code>chain</code> value by <code>address</code>, were all changed to True for <code>chain</code>.
- Eateries with the same <code>name</code> at the same <code>address</code>, but different <code>num_seats</code> were changed to the mean.
- Eateries with more than 2 values in the <code>address</code> column were changed to/kept as True for the <code>chain</code> column.
- <code>name</code> and <code>address</code> values tweaked to be more uniform to identify hidden dupplicates. 

*Irrelevant data*
- Removed grocery stores as they are not eateries (but kept eateries within grocery stores).

*Missing data*
- The three Null values in the <code>chain</code> column were changed to False based on Google research.

*Duplicate data*
- No full duplicates were identified. Duplicate rows were identified (and dropped) when managing missing & errored data.

**97% of data remains.** 

### Exploratory analysis
*General features
- The proportional breakdown by <code>type</code> of establishment (restaurant, bakery, fast food, pizza, cafe).
- The proportional breakdown by the <code>chain</code> column (True vs. False); further broken down by <code>type</code>.
- The correlation between number of locations (<code>address</code>) and <code>chain</code>.
- Whether there exists a correlation between the <code>chain</code> and <code>num_seats</code> columns.
- Whether there exists a correlation between the <code>type</code> and <code>num_seats</code> columns.

*Location specific

### Conclusion
