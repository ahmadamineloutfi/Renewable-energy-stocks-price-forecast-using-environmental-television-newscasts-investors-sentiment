# Introduction
The world is turning towards renewable energies to sustainably meet its increasing demand for energy. Naturally, this is being accompanied by a strong momentum in trading within the renewable energy market. Today, behavioral finance acknowledges the major role of wider psychological and social factors in shaping the stock market, through influencing investors’ sentiment. Therefore, this paper explores the understudied question of whether environmental television newscasts can be used as a proxy for measuring investors’ sentiment and in helping to improve the forecast accuracy of renewable energy stock prices. First, we compute the sentiment scores of the environmental newscasts of CNN, BBC News, MSNBC, and Fox News. We then use machine learning to implement a baseline forecast model, as well as an augmented one which takes the newscasts’ sentimentscores as input. Using four different accuracy metrics, we find that environmental TV newscasts can improve the forecast accuracy of renewable energy stock prices in 78% of the experiments, and decrease the Mean Absolute Error, Mean Squared Error, and Root Mean Squared Error in 83.3% of the experiments. We also find that the sentiments of conservative news outlets, such as Fox News, can improve the forecast accuracy of renewable energy stock prices more than liberal ones. Finally, we provide some insights into potential psychological dynamics that can help us make sense of the results, such as the negativity bias theory.

# Author:
Ahmad Amine Loutfi.

# Data:

Target variable: the daily adjusted stock prices of renewable energy firms between July 2, 2009, and January 21, 2021. They include renewable energy firms listed in the WilderHill Clean Energy Index (ECO), which is widely used as a benchmark for clean energy stocks

Explanatory variables:

- Conventional data: the S&P 500 index, VIX index, and US Dollar/USDX –  Index-Cash, between July 2, 2009, and January 21, 2021.
- Spoken Environmental TV newscasts data from the four major US TV newscasts channels: CNN, BBC News, MSNBC, and Fox News making a total of 92800 rows of text that maps to the period between July 2, 2009, to January 21, 2021. 

# LSTM Model:
Our final dataset is made up of 3856 rows of data which maps to the periods between July 2, 2009, and January 21, 2021. The dataset was split into a training set (the first 2458 days), a validation set (the next 820 days) and a test set (the last 578 days).
We implemented the same LSTM neural network architecture. For its design, we followed the principle of simplicity, where we kept the model at 1 hidden layer. To prevent overfitting, we leveraged the dropout regularization technique (Kali Ali & Boughaci, 2022) as well as early stopping while restoring the best weights (Bentoumi et al., 2022). For the activation functions, we used RELU and for the recurrent activation we used Sigmoid (Dubey et al., 2022). To determine the number of hidden neurons for each renewable energy firms’ stock, we used the following industry-standard formula: 𝑁ℎ =𝑁𝑡/ (𝑁𝑖+𝑁𝑜) where 𝑁ℎ is the number of hidden neurons, 𝑁𝑡 is the number of samples in training data set, 𝑁𝑖 is the size of the input neurons, 𝑁𝑜 is the size of output neurons, and 𝑎 is an arbitrary scaling factor usually between 2 and 10. "Furthermore, given the strong relationship between the loss function and the model’s lookback and performance, we allowed each model to run on a range of lookback values” (Loutfi et al., 2022, p. 9)that ranged from 1 to 3. Finally, for optimization we used Adam algorithm which “combines the best features of AdaGrad and RMSProp algorithms so that it makes it possible to handle sparse gradients on noisy problems” (Kohli et al., 2022, p. 232).

# Environmental TV Newscasts dataset:
'NLP.zip'.

# Python File:
'environmental_tv_newscasts.py'.
