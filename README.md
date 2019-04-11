# Starbucks Capstone
### Udacity Starbucks Challenge
This project provides analysis and a predictive model for a data set which simulates a period
of time over which users of Starbucks' mobile app receive promotional offers and make purchases.

### Table of Contents

1. [Libraries and Installation](#installation)
2. [Project Description](#motivation)
3. [Files](#files)
4. [Findings](#results)

## Libraries and Installation <a name="installation"></a>

Libraries used:
The following libraries were used for the primary analysis, and are standard in the Data Science discipline:
 - pandas
 - numpy
 - matplotlib
 - seaborn
 - sklearn
 - pickle

## Project Description<a name="motivation"></a>

The objective of this project is to use the transaction log to describe and predict customer behavior, and determine if a measurable
difference exists before and after receiving an offer.

Specifically, I am looking for a quantifiable trend in terms of:

1. Customer demographics, described by age, gender, income, and membership period
2. Nature of the offer, including delivery channel, type of offer, difficulty, and reward
3. A customer's behavior when not given an offer

These values are investigated using aggregate statistics for each demographic segment, and predicted using a regression model.


## Files <a name="files"></a>

The analysis and summary explanation can be found in the Jupyter Notebook "Starbucks_Capstone_Challenge.ipynb".  Exploratory code is contained in the notebook "Starbucks_Capstone_preliminary.ipynb", which is not critical to the project.  Exploratory code may not be complete or remain functional.  It is included for archival and informational purposes and is not intended to be evaluated against project rubric with respect to proper software engineering principles or functionality.

The relevant datasets are "portfolio.json", "profile.json", and "transcript.json", and originate from Starbucks by way of Udacity.

The data files indicated above capture the data relevant to the 2013-2018 timeframe.

## Findings<a name="results"></a>

Briefly, the analysis shows:

1. On a whole, the customers were receptive to the offers.  There were few instances where a deomgraphic reduced busioness on receiving an offer.

2. Specific heuristics include:
Gender:
Male users increased transaction frequency as a result of BOGO offers more than Females or Others.
However, Female users spent more per transaction than Males or Others as a result of BOGO offers.
A slight decrease in transaction rate was recorded for Females as a result of Discount offers, compared to a slight increase for Males and Others.
Discounts increased average transaction value significantly more for Females and Others than Males.

Income:
BOGO Transaction rate correlates to income - low income earners increase transaction rate, while there is a small decline for upper earners.
There is little to distinguish average value.
Discount transactions correlate similarly to income, but there is an increase in average transaction value for higher earners.
Informational offers decline in both transaction volume and average value for higher income earners

Age:
Bogo offers drive higher increase in transaction rate for younger users, but older users spend more
Discount offers decline by age and no trend is observed for average value.
No trends were observed for informational offers

Reward and Difficulty:
Younger and lower-income customers increased transaction rate overall, but independently of reward and difficulty.

Membership Period:
Users who had been members longer responded with considerably greater transaction volume increase (joined_2018 saw consistent decreases).
The average value had a non-linear trend, reaching a peak for mid-period (2014-2016)
joiners, and the longest and shortest were the least.  (This probably impacted my linear regression model.)
Discount and info offers had a similar trend for membership period.  

3. Creating a regression model
I evaluated a linear model using the one-hot encoded gender, age, income, and member_for values.  R^2 values were low.
By scaling and normalizing the data, I was able to increase the R^2 to approximately 0.24 for transaction rate and 0.1 for average value.
I added the information on reward and challenge values, with a resulting minor increase in R^2.

Adding the channels did not result in a material impact to performance.

A summary of the findings is published here:
https://ismith1024.github.io/Starbucks_Capstone/





