# Market Research on Restaurants in Los Angeles

:point_right: View the **notebook** [here](https://nbviewer.org/github/tpeckerman/practicum_projects/blob/main/Market%20Research/Market%20Research%20on%20Los%20Angeles%20Restaurants.ipynb) using nbviewer.\
:point_right: View the **presentation** [here](https://github.com/tpeckerman/practicum_projects/blob/main/Market%20Research/Robot%20Run%20Caf%C3%A9%20in%20LA.pdf).

## In this folder

| File name | Description |
| --- | --- |
|*rest_data.csv* | Data on food establishments in Los Angeles |
|*cafe_market_research.ipynb* | Analysis of trends in eateries in Los Angeles. |
|*cafe_market_research-presentation.pdf*| PDF version of the final pptx presentation of summarized findings |

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
*(Suspected) Errored data* 
- Replaced eateries with one seat to Null for the <code>num_seats</code> column.
- Bakeries with one location were changed to False for the <code>chain</code> column.
- Eateries for which there was a discrepency between the <code>chain</code> value by <code>address</code>, were all changed to True for <code>chain</code>.
- Eateries with the same <code>name</code> at the same <code>address</code>, but different <code>num_seats</code> were changed to the mean.
- Eateries with more than two values in the <code>address</code> column were changed to/kept as True for the <code>chain</code> column.
- <code>name</code> and <code>address</code> values tweaked to be more uniform to identify hidden dupplicates. 

*Irrelevant data*
- Removed grocery stores as they are not eateries (but kept eateries within grocery stores).

*Missing data*
- The three Null values in the <code>chain</code> column were changed to False based on Google research.

*Duplicate data*
- No full duplicates were identified. Duplicate rows were identified (and dropped) when managing missing & errored data.

**<div align="center">97% of data remains.</div>**

### Exploratory analysis
*General features*
- Proportional breakdown by <code>type</code> of establishment (restaurant, bakery, fast food, pizza, cafe).
- Proportional breakdown by the <code>chain</code> column (True vs. False); further broken down by <code>type</code>.
- Correlation between number of locations (<code>address</code>) and <code>chain</code>.
- Correlation between the <code>chain</code> and <code>num_seats</code> columns.
- Correlation between the <code>type</code> and <code>num_seats</code> columns.

*Location specific*
- Identification of top 10 streets with the most eateries on them.
- Seat count distributions of the top 10 streets with the most eateries.
- Identificatopm of streets containing only one eatery.

### Conclusion
1. <ins>Type</ins>: The market is not saturated by Cafes which represent between 4% to 18% of the market (the latter when not considering Restaurants). The percentage of the market is around the same for the top 10 streets. While you would be competing with big chains and their heavy resources, the culture trend is moving more towards new age or bohemian specialty cafes. Also, even as the novelty wears off, the convenience of quick service, delicious food, and unique atmosphere would help maintain business.

2. <ins>Location</ins>: On one of the top 10 streets as this would be the lowest risk and most visible to the potential consumers.

3. <ins>Number of seats</ins>: Between 20 and 35; 20 because that would be safe and 35 so there is room for growth.
