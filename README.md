Overview

Residential brokerage is a very competitive industry and in order to get a leg up on the competition, the brokerage has decided to offer homeowners/clients complimentary consulting on how they can maximize the value of their home before putting it on the market.  They have hired me to analyze Kings Country housing market data to determine how best to advise their clients' home renovations.

Data Understanding

I will create a linerar regression model to analyze housing price changes based on the changes on independent variables based on King County real estate data.  We will make two recomendations to clients on how they can add the most value to their home. Recomendations will be based on a linear regression model because it allows us to quantify how unit changes in independent variables will affect our dependent variable, price.
Baseline: Once we cleaned the data, ie no null values and it was converted to numeric form, we modeled our baseline. While it had the highest r-squared score it lacked normality, it was heteroscedastic (the variance in residuals was uneven), and there were independent variables with unusable p-values (they were too large to reject the null hypothesis).

Modeling

Model 1: we took out outliers in data and only dropped about 10% of the data set in the process.  Our r-score dipped meaning less of the variance could be explained by the model which is a bad thing but our RMSE improved greatly and so did our normality and homoscedasticity.

Model 2: We wanted to improve r-score so we created catagorical variables aka coefficients for each level of floor, bathroom, bedroom etc.  Doing so actually raised the r-score to its highest level since the baseline to almost 50 and dropped the RMSE to $140,000, which is the expected error between true value and the value our model predicts.  Although one may consider this a relatively large error relative to home value.  The problem with this model was the p-values for the some of the variables, many of them became way to large to be usable.

Model 3: We did feature scalling to further normalize our data but removed catagorical variables.  Log transformations were used to fit the data.  All of the p-values were usable but we went backwards with homoscedasticity, linearity, r-score and RMSE.

Final Model: We added catagories for some of the variables, only the ones that didn't have high p-scores from model 2.  As a result improved our r-score, RMSE, normality, homoscedasticity, and linearity from the previous iteration and have no high p-values in our data that would prevent us from rejecting the null hypothesis.

Conclusion

Square feet of living space has a coefficient of 96.25 or $96.25 per each additional foot.  If clients can add additional living space over a garage or extend a part of the house for cheaper than this amount, then we would advise our clients to do so.
Condition has a coefficient of 40900 or $40,900 for each unit increase.  Condition is rated on a scale of 1-5 and each level you move up should add about $40,900 in value.  The worse condition a client's house is in, the greater we would recommend a complete renovation.  If a client current has a 2 condition or fair-badly worn, then he/she can realize added value of almost $123,000 by bringing it to a 5.
