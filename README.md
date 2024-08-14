## Book Popularity Analysis

### Task
To analyze the role of information revelation in the popularity of English-language fiction books

### Data
To analyze the role of information revelation, we utilized datasets from Project Gutenberg. The first dataset (metadata.csv) consists of book-level attributes, the second dataset (kldscores.csv) consists of book-ids and its corresponding narrative-revelation scores formatted in the form of list, the third dataset (extracontrols.csv) consists of attributes subjected to genres and controls like speed, sentiment average, sentiment volume, wordcount.

### Steps Performed for Analysis
1)	Book-level measures of KLD_values are built like minimum, maximum, range, mean, variance, standard deviation, median, slope and intercept of Linear Regression, autocorrelation, and entropy.
2)	Existing datasets are merged with the newly created dataset i.e., book-level measures on book-id and a new column is created for book popularity which is equal to log(downloads).
3)	From the correlation matrix of book popularity, it is known that the variables which strongly impact the book popularity are downloads, wordcount, sentimental volume, entropy, speed, range, maximum, standard deviation, slope, sentimental average, variance.

### Analysis
From the regression model analysis, it is concluded that the model is moderately fit with an R2 value of 21.1%, it is statistically significant as the p-value of F-statistic is 0.00. Independent variables which are statistically significant has the p-value < 0.05. Independent variables like downloads, Max_KLD, Range_KLD, Var_KLD, Std_KLD, and controls like speed, sentiment_avg, and sentiment_vol are statistically significant with the book popularity explaining the 21.1% variation in the model. The value of Durbin-Watson is less than 2 indicates that there is no auto correlation in the model.
