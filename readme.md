# Prosper Loan Data Exploration

## by Andrey Kabanov

## Dataset

Analysis & data findings were performed on the Prosper loan data. The dataset consists of about 113,000 records (loans). There are 81 sepparate (features) columns in the dataset. I chose a subset of them to find any relationships between the interest rates of the loans.

## Summary of Findings

I expected that the various different credit risk scores associated with each loan and income/debt related features would be the most advantageous in this analysis. My initial intuition was correct and the majority of the features chosen were correlated with the interest rate columns, with `ProsperRating (Alpha)` or it's numeric variant `ProsperRating (numeric)` being highly correlated. 

The others weren't as correlated, and I looked deeper into why the proprietary `ProsperScore` wasn't as correlated and turned out that when looking at multivariate relationships that the values for the `ProsperScore` column were distributed acorss all levels of the `ProsperRating(s)`. What this means is that a loan with a low/wrose `ProsperRating` could have a good/high `ProsperScore` and vice-versa. This implies that other criteria not explored in the analysis are used to determine the `ProsperScore` and it would be a good place for future anaylsis to begin.

Another variable that I though would be related was the `DebtToIncomeRatio` but it turned out to have a very low correlation to the interest rate columns. The distribution also contained extreme outliers and when exploring it's distribution the x-axis had to be adjusted to see a normally distributed histogram between values of `0` and `1.5` with a left skew.

In exploring how the interest rate of a loan is affected by the loans `Term` (length of loan) I discovered that under every `ProsperRating` shorter term loans had a lower interest rate. Unsurprisingly those with a higher/better `ProsperRating` had a lower interest rate.

## Key Insights for Presentation

If you want a lower interest rate on a loan from Prosper you should have a low credit risk, ie. a higher/better `ProsperRating [Alpha/numeric]` and consider taking out a 12 over 36 month or 36 over 60 month long term loan.

## Resources
* Prosper [data dictionary](https://docs.google.com/spreadsheet/ccc?key=0AllIqIyvWZdadDd5NTlqZ1pBMHlsUjdrOTZHaVBuSlE&usp=sharing)
* pandas documenation
* matplitlib documentation
* seaborn documentation
* [Example Project](Example%20Project/Example_Project_Diamonds_Part1.html) from Udacity

