## Book Popularity Analysis

### Goal
To analyze the role of information revelation in the popularity of English-language fiction books

### Datasets
To analyze the role of information revelation, we utilized datasets from Project Gutenberg
1) The dataset ```metadata.csv``` consists of book-level attributes including download counts
2) The dataset ```kldscores.csv``` consists of book IDs and their corresponding narrative-revelation scores formatted in the form of Python lists. These scores measure the amount of information revelation scores in terms of Kullback-Liebler divergence, for each subsequent section of the corresponding book.
3) The dataset ```extracontrols.csv``` consists of attributes subjected to genres and controls like speed, sentiment average, sentiment volume, and word count.

### Execution
Run ```Book_popularity.ipynb``` file

### Steps Performed for Analysis
1)	Book-level measures of KLD_values are built like minimum, maximum, range, mean, variance, standard deviation, median, slope, and intercept of Linear Regression, autocorrelation, and entropy.
2)	Existing datasets are merged with the newly created dataset i.e., book-level measures on book-id, and a new column is created for book popularity which is equal to log(downloads).
3)	From the correlation matrix of book popularity, it is known that the variables that strongly impact book popularity are downloads, word count, sentimental volume, entropy, speed, range, maximum, standard deviation, slope, sentimental average, and variance.

### OLS Regression Analysis
The OLS(Ordinary Least Square) regression analysis examines the relationship between several book-level measures (independent variables) and book popularity (dependent variable). If a variable has a p-value < 0.05 then it has a potential contribution in the model. 
From the regression model analysis, it is concluded that the model is moderately fit with an R2 value of 21.1%, it is statistically significant as the p-value of F-statistic is 0.00. Independent variables that are statistically significant have a p-value < 0.05. Independent variables like downloads, Max_KLD, Range_KLD, Var_KLD, Std_KLD, and controls like speed, sentiment_avg, and sentiment_vol are statistically significant with the book popularity explaining the 21.1% variation in the model. The value of Durbin-Watson is less than 2 indicating that there is no autocorrelation in the model.

### Lasso Regression Analysis
LASSO regression simplifies the model by shrinking some coefficients to zero. It automatically performs feature selection by shrinking less relevant features' coefficients to zero. The results indicate that downloads and word count are the most significant predictors of book popularity among the considered book-level measures, and control variables. 
```
LASSO Regression Coefficients
Variable	Coefficient
downloads	0.000693
wordcount	0.000003
```
