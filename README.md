# Introduction
The world is turning towards renewable energies to sustainably meet its increasing demand for energy. Naturally, this is being accompanied by a strong momentum in trading within the Renewable Energy (RE) market. Today, Behavioral Finance (BF) acknowledges the major role of wider psychological and social factors in shaping the stock market, through influencing Investors’ Sentiment (IS). Therefore, this paper explores the understudied question of whether environmental television newscasts can be used as a proxy for measuring Investors’ Sentiment and in helping to improve the forecast accuracy of Renewable Energy stocks price. First, we compute the sentiment scores of the environmental newscasts of CNN, BBC News, MSNBC, and Fox News. We then use machine learning to implement a baseline forecast model, as well as an augmented one which takes the newscasts’ sentiment scores as input. Using four different accuracy metrics, we find that environmental TV newscasts can improve the forecast accuracy of RE stocks price in 78% of the experiments, and decrease the MAE, MSE and RMSE in 83.3% of the experiments. We also find that the sentiments of conservative news outlets, such as Fox News, can improve the forecast accuracy of RE stocks price more than liberal ones. Finally, we provide some insights into potential psychological dynamics that can help us make sense of the results, such as the negativity bias theory.

# Author:
Ahmad Amine Loutfi.

# Data:
The dataset of this study is made up of two parts:
1.	Target variable: the daily adjusted stock prices of RE firms were collected from Yahoo Finance, between July 2nd, 2009, and January 21st, 2021. They include RE firms listed in the WilderHill Clean Energy Index (ECO), which is widely used as a benchmark for clean energy stocks (Yahoo Finance, 2022).
2.	Explanatory variables:

    2.1. Conventional data: the S&P 500 index, the stock market volatility represented by the VIX index, and the USD exchange rate represented by US Dollar/USDX – Index-Cash were collected from Yahoo Finance, between July 2nd, 2009, and January 21st, 2021 (Yahoo
    Finance, 2022).

    2.2. Spoken dataset was collected from the four major US TV newscasts channels: CNN, BBC News, MSNBC, and Fox News making a total of 92800 rows of text that maps to the period between July 2nd, 2009, to January 21st, 2021 (Singh, 2020).
    LSTM Model:

Our final dataset is made up of 3856 rows of data which maps to the periods between July 2nd, 2009, and January 21st, 2021. The dataset was split into a training set (the first 2458days), a validation set (the next 820 days) and a test set (the last 578 days). To draw a meaningful comparison between the forecast accuracy of the baseline and the newscasts-augmented models, it was important that we choose the same algorithm for both models. Therefore, we implemented the same LSTM neural network architecture. For its design, we followed the principle of simplicity, where we kept the model at 1 hidden layer. To prevent overfitting, we leveraged the dropout regularization technique as well as early stopping while restoring the best weights. For the activation functions, we used RELU and for the recurrent activation we used Sigmoid. To determine the number of hidden neurons for each RE firms’ stock, we used the industry-standard formula:N_h= N_t/(a (N_i+N_o)) where N_h is the number of hidden neurons, N_t is the number of samples in training data set, N_o is the size of the input neurons, is the size of output neurons, and a is an arbitrary scaling factor usually between 2 and 10. Finally, for optimization we used Adam algorithm .
Environmental TV Newscasts dataset:

# Dataset: 
- 'NLP.zip'.

# Python File:
- ‘RE_stocks_price_forecast using_environmental_TV_newscasts_IS.py’.

# References:
-	Yahoo Finance. (2022). Historical daily adjusted stock prices of firms in the WilderHill Clean Energy Index (ECO) [API data]. https://finance.yahoo.com/.
-	Singh, A. (2020). Environmental News NLP Dataset. https://www.kaggle.com/datasets/amritvirsinghx/environmental-news-nlp-datase.

