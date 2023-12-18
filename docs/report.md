# DATA606 - Capstone Proposal 

## Title and Author
- **Title** : Netflix stock price prediction
- **Author** : Thulasi Gabbita
- **Semester** : Fall 2023
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- [GitHub](https://github.com/ThulasiGabbita57)
- [LinkedIn](https://www.linkedin.com/in/thulasi-gabbita/)
- [PowerPoint presentation file](https://github.com/DATA-606-2023-FALL-TUESDAY/Gabbita_Thulasi/blob/main/docs/DATA606_FinalPresentation.pptx)
- [YouTube video](https://youtu.be/SlcBwcVQDhc)

    
## Background
The Dataset contains stock price of the stock "Netflix" for the five years period i.e., from 5th Feb 2018 to 5th Feb 2022. This Data includes columns such as Date, Open, Close, High, Low, Volume, and Adjusted Close.

The art of forecasting stock prices has been a difficult task for many of the researchers and analysts. In fact, investors are highly interested in the research area of stock price prediction. For a good and successful investment, many investors are keen on knowing the future situation of the stock market. Good and effective prediction systems for the stock market help traders, investors, and analyst by providing supportive information like the future direction of the stock market.

**Research Questions**
1. Can we develop accurate predictive models for stock price using machine learning techniques like linear regression, logistic regression, decision trees, etc?
2. Which evaluation metrics (e.g., Mean Absolute Error, Root Mean Squared Error, Sharpe Ratio) should be used to assess the performance of the stock price prediction models?
3. Which machine learning models (e.g., linear regression, decision trees, neural networks, time series models) are most suitable for stock price prediction, and how do their performance compare?
4. What are the optimal hyperparameters for the selected machine learning models to achieve the best predictive performance?
5. What insights can be gained from exploratory data analysis, such as identifying patterns, correlations, or anomalies in the historical stock price data?
6. What features derived from the raw data (e.g., moving averages, technical indicators, volatility measures) are most effective in improving prediction accuracy?
7. What are the most common data quality issues (e.g., missing values, outliers) in stock price datasets, and how can they be effectively addressed in the preprocessing stage?
8. Are there ethical considerations in using stock price prediction models, such as potential market manipulation or unintended biases in trading decisions?
9.  Can the models be deployed for real-time stock price prediction, and what are the challenges associated with maintaining accuracy in a dynamic market environment?


## Data 

**Describe the datasets you are using to answer your research questions.**

- Data sources: https://www.kaggle.com/datasets/jainilcoder/netflix-stock-price-prediction
- Data size: 74 KB
- Data shape: # of rows - 1009 and # columns - 7
- Time Period - The Dataset contains data for 5 years ie. from 5th Feb 2018 to 5th Feb 2022

**What features are important, what column means what**

1. Date - Provides recorded date of that observation
2. Open - States the price at which stock opened
3. High - Provides particular date High price
4. Low  - Provides particular date Low price
5. Close - Close price adjusted for splits
6. Adj Close - Adjusted close price adjusted for splits and dividend and/or capital gain distributions
7. Volume - Volume of stocks traded

**Target Variable - Close**

## EXPLORATORY DATA ANALYSIS (EDA)

In order to completely understand the dataset, EDA was performed. Exploratory data analysis helps us to understand the dataset, relationships and correlation amoung different data points, reliability of the data, valuable insights and patterns, enabling us to make data driven decisions and model choices.

**Preliminary data analysis**
Preliminary analysis was conducted to check for dataset size and shape, data type of the columns, missing values, and statistical summary of numerical variables. Methods used are:
- df.info()
- df.describe()
- df.isnull().sum()

From above steps, I observed dataset is clean and ready to use. Hence, no further cleaning required.

For further ease and convenience, the **Date** column was set as index and a new **Formated Date** column was created

**Visualizations**
1. Visualization of all price values: Below plot shows us how the Open, High, Low, Close, Adj Close, Volume, Formated Date of Netflix stock has changed over the five years from Feb 2018 to Feb 2022.
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/img1.png">
2. Distribution and variation in **Close** price: These plots mainly focuses us illustrates the distribution and variation of our target variable **Close** price
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/img2.png">
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/img3.png">
3. Daily Returns: The daily returns of the netflix stock price over the 5 year period was calculated and stored in a new column **Daily Returns**. below graphs depicts the distribution of daily returns percentage and visualization of daily returns for the 5 years.
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/img4.png">
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/img5.png">
4. Cumulative Returns: Here, Cumulative returns of netflix from 2018 to 2022 were caluculated and stored in **Cumulative Returns** column and visualized.
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/img6.png">
5. Plot comparision of closing price and moving average: Moving average, being one of the most used parameter in analysis of stock prices, was calculated. The **Close** price was compared against daily moving average for 30 day window.
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/img7.png">

## Model training:
- The train vs test split of 80/20 was used
- Models used for predictive analysis:
  - Linear Regression
  - Random Forest classifier
  - ARIMA
- Python packages used for this project include:
  - scikit-learn
  - statsmodels
  - matplotlib
  - Pandas
  - numpy
  - seaborn
- The development environments used include:
  - Jupyter Notebook
  - Visual Studio Code

After performing Linear Regression and Random forest classifier models on the Netflix dataset it was observed that models are overfitting the data and not suitable for analyzing time series data. Hence, ARIMA model was used to obtain final predictions

**ARIMA model**  
ARIMA model helps us to evaluate time series data. As ARIMA has to be performed on stationary data, ADFuller test needs to be conducted to test data stationarity. 

- Testing data stationarity using ADFuller Test
  - In ADFuller test, we will analyze the p-value, if p-value is less than or equal to 0.05, it indicates strong evidence against null hypothesis. So, we can reject the null hypothesis indicating data is stationary
  - In the other case, if p-value is greater than 0.05, it indicates time series data has a unit root, weak evidence against null hypothesis and data is not stationary.
  - For Netflix data set, initial p-value was observed as 0.3 which is greater than 0.05 so data is not stationary.
  - After differencing the data, p-value was observed below 0.05 stating data is stationary

ARIMA model was performed on the differenced data(stationary data) and r2 score was observed as 0.97

**forecasting values for next 30 days**
1. Below plot shows us the forecasted values of Netflix stock for next 30 days.
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/image.png">

**Predicted Values (ARIMA) vs Original Price**
1. Below plot shows us the predicted values of Netflix stock using ARIMA model vs Original Price of Netflix stock
<img width="600" alt="image" src="https://github.com/ThulasiGabbita57/UMBC-DATA606-FALL2023-TUESDAY/blob/main/newplot.png">

## Challenges: 
- Performing EDA with an unconventional approach of using statistical data like cumulative returns, moving average  
- Training and prediction of time series data using ARIMA model  

## Lessons Learned: 
- Analysis of time series data 
- Finding different parameters and their scope in analyzing stock price data 
- Time series forecast using ARIMA

## Conclusion:  
- Linear Regression and Random Forest models were overfitting the data and not suitable to analyze time series datasets
- ARIMA can be used to analyse time series data after checking for data stationarity
- Even thouogh stock price predictions are not fully reliable we can use them to certain extent like how the stock price will go in future, what are the possible ranges of price, etc.



