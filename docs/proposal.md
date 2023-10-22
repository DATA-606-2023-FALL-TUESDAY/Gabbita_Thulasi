# DATA606 - Capstone Proposal 

## Title and Author
- **Title** : Netflix stock price prediction
- **Author** : Thulasi Gabbita
- Prepared for UMBC Data Science Master Degree Capstone by Dr Chaojie (Jay) Wang
- [GitHub](https://github.com/ThulasiGabbita57)
- [LinkedIn](https://www.linkedin.com/in/thulasi-gabbita/)
- **Link to your PowerPoint presentation file** - In Progress
- **Link to your YouTube video** - In Progress

    
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
- Models using for predictive analysis:
  - Linear Regression
  - Random Forest classifier

