# Risk of Loan Default

:point_right: View the **notebook** [here](https://nbviewer.org/github/tpeckerman/practicum_projects/blob/49f080cc3654af0da2519ebcf0354b15766c30e7/Risk%20of%20Loan%20Default/risk_of_loan_defaults.ipynb) using nbviewer.


## In this folder

| File name | Description |
| --- | --- |
|*credit_scoring_eng.csv* | Data on customer characteristics|
|*risk_of_loan_defaults.ipynb* | Analysis of customer characteristics and risk of default. |

## Project Description

### Objective
The bank's loan division is seeking to build an internal credit scoring system that evaluates a potential customer's likelihood to repay a loan. This analysis will help to determine what customer characteristics may be correlated with a defaulted loan in effort to decrease the overall default rate on loans.

### Libraries to run the notebook locally
<b> *Python version 3.8.8* </b>
|Library| Version|
| --- | --- |
|pandas|1.3.1|
|seaborn|11.0|
|matplotlib.pyplot|3.3.2|
|numpy|1.19.2|

  
## Project Overview

### Data processing
*Cleaning and (Suspected) Errored data* 
- All values for the <code>education</code> field were changed to lowercase.
- <code>Education_id</code> and corresponding <code>education</code> values more switched arount to be intuitively related.
- Rows with neagtive and 20 values for the <code>children</code> column were deleted.
- All values where <code>days_employed</code> == 'retiree' were changed to 0.
- All values where <code>dob_years</code> == 0 were replaced by the mean of the column.
- The value 'XNA' for the <code>gender</code> column was changed to 'unkown' (one occurance).
- Rows where <code>income_type</code> == 'unemployed', 'student', 'entrepreneur', and 'paternity / maternity leave' were dropped (six occurances).

*Missing data*
- Used the median income of the <code>education</code> and <code>age_group</code> columns grouped to populate the missing values for <code>total_income</code> (found in <code>new_income</code>).

*Duplicate data*
- 71 duplicate rows were dropped.

**<div align="center">99% of data remains.</div>**

### Exploratory analysis
*General features*
- Categorized data 3 ways and tested for correlation with defaulting on a loan:
  1. <code>family_status</code> and <code>children</code> combined (2 person income & children, 2 person income & no children, 1 person income & children, 1 person income & no children).
  2. <code>purpose</code> (property, education, wedding, car)
  3. <code>new_income</code> by quartile ('low', 'medium low', 'medium high', and 'high').
 
### Conclusion
1. Clients with no children are least likely to default, followed by the potential for a 2 income household.
2. Clients who took out a loan to finance their property or wedding are signiciantly less likely to default than clients who took out a loan for a car or education. This may be because property is an asset that often increasing in value and wedding loans can be paid back with monetary gifs from the wedding.
