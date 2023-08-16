# Machine Learning Project
## Introduction
  In finance, mutual funds are an example of the expert problem. Mutual funds are a portfolio of investments managed by a fund manager, or expert investor. These funds charge a high premium because the funds are expected to perform well compared to the market; however, historically, almost 75 percent of mutual funds fail to beat the market (however this dataset used data from 2016-17 in which only 66 percent failed to beat the market). So, for my final project, I chose a dataset of mutual funds. The data set contains fundamentals for each mutual fund, such as the price to earnings ratio, beta, total net assets, etc. I want to create a model using five features that can accurately predict whether a mutual fund will beat the market. (Extra) Before using the data, I had to remove all of the mutual funds that were bond funds because the return on bonds is much smaller than the return on stocks and I am comparing the returns of each mutual fund to the returns of the S&P 500, the stock market. Furthermore, for k-nearest neighbor, I had to standardize all of the data. Some features contained values in the billions, whereas other features had values within 0 and 1.
## Strategies
### K-Nearest Neighbor
  The first technique I chose is k-nearest neighbor. This was a no brainer because my dataset contains over 15,000 datapoints, so techniques that take a long time to train are not an option. Furthermore, k-nearest neighbor becomes slow as the number of features grows. This does not affect my models because I am using just five features. Lastly, k-nearest neighbor is very accurate, especially when the dataset is large like in this case. I chose 5 features (from the 21 total features) for 16 different models at random. I would have liked to have chosen more but just 16 models took 20-25 minutes. I ran cross validation for each model with the test size being one percent of the total dataset.
### Logistic Regression
  The second technique that I chose was logistic regression. This may not have been the best method because training time is lengthy; however, it is a technique that I am comfortable
With and the results are intuitive. Plus, does not tend to overfit when the feature space is small (in hind site I could have checked the r-squared values for my models and run t-tests). I created X different logistic regression models (runtime was very restricting in this case) and used cross-validation (test size being one percent of the dataset as with k-nearest neighbor).
## Results
  The most accurate model using k-nearest neighbor model correctly predicted whether a mutual fund beat the market or not 94.8 percent of the time. Of the 154 test datapoints, the model correctly predicted that 40 mutual funds beat the market and 106 did not beat the market. It failed to predict that 3 beat the market and 5 did not. This model used the predictors: “size,” “Morningstar rating,” “% basic materials,” “% real estate,” and “% healthcare.” I conclude that k-nearest neighbor is a very good model for this prediction.
  The most accurate model using logistic regression correctly predicted whether a mutual fund beat the market 71.4 percent of the time using the features: “% financial services,” “returns 2016”, “beta”, “size”, and “net annual expenses.” For some reason, the logistic regression model always predicts that the mutual fund will fail to beat the market not matter how many test points there are. In conclusion, this is a poor model.
  From this, I made a few interesting observations. One, return in previous years was only used once between the two models (“returns 2016” in the regression model). The dataset contained returns from 2015, 2016, and 2017. Therefore, based on the models, the fact that a mutual fund beat the market in past years does not help us to predict whether the fund will beat the market in the current year (or it is at least less helpful than the other predictors). Two, “size” was used in both models. Therefore, we have reason to conclude that, if a mutual fund has a lot of investors and is large, this is for a reason.
