# Data Analysis: Client VM

This project focuses on analyzing data related to an influencer's work in 2024. The goal is to explore the data to identify areas for improvement and create a predictive model to estimate monthly earnings based on hours worked.

---

## Objectives

- **Explore the client's data to extract useful insights about their work in 2024.**
- **Perform exploratory data analysis to create a predictive model for estimating monthly earnings based on hours worked.**

---

## Tools and Libraries

The project uses the following Python libraries:

- **NumPy**: For numerical computations.
- **Pandas**: For data manipulation and analysis.
- **Seaborn**: For data visualization.
- **Matplotlib**: For creating plots and charts.
- **Scikit-learn**: For machine learning tasks, including linear regression, random forest regression, and model evaluation metrics.
- **Prophet**: For time series forecasting.

---

## Data

The data is loaded from two Excel files:
- Private data

The data includes information about the influencer's work, such as:
- Hours worked (`Minutos_trabalhados`)
- Tokens earned (`Tokens`)
- Tokenage points (`Meio`)
- Period of the day (`Periodo`)
- Date (`Data`)

---

## Analysis

### Data Loading and Initial Exploration
The data is loaded into a Pandas DataFrame, and initial exploration is performed to understand the structure and content of the data.

### Grouping and Aggregation
- Tokens are grouped by tokenaged points (`Meio`) and summed to identify the most profitable.
- Tokens are grouped by period of the day (`Periodo`) to analyze earnings by time of day.
- Tokens are grouped by month and week to analyze trends over time.

### Visualization
- **Tokens by ways to tokenize**: A line plot shows the sum of tokens earned by each way.
- **Tokens per Minute Worked**: A bar plot shows the average tokens earned per minute worked.
- **Monthly Trends**: A bar plot shows the average tokens earned per minute by month.
- **Weekly Trends**: A bar plot shows the average tokens earned per minute by week.
- **Period of the Day**: Bar plots show total and average tokens earned by period of the day.

### Predictive Modeling
#### Simple Linear Regression
- A linear regression model is trained to predict tokens earned based on hours worked.
- The model achieves an R² score of **0.79**, indicating a strong correlation.

#### Time Series Forecasting with Prophet
- A more complex model using Facebook's Prophet is implemented to incorporate temporal features (e.g., month, sine/cosine transformations).
- Cross-validation is performed to evaluate the model's performance.

---

## Key Insights

1. **Most Profitable ways to tokenize**: Tips, Gift, and Talk were the most profitable ways, with a significant disparity compared to others.
2. **Optimal Working Hours**: The highest average tokens per minute were earned when working between **30 minutes to 1.5 hours** per day. Working **8 hours** also showed high earnings, but **4.5 hours** was the most common.
3. **Monthly Trends**: May, June, and July were the most profitable months, while December had the lowest earnings.
4. **Weekly Trends**: The second week of the month was the most profitable, but the differences between weeks were minimal (less than 1 token per minute on average).
5. **Time of Day**: Morning was the most productive period, with the highest average tokens earned.

---

## Predictive Model Results

### Simple Linear Regression

#### Results
- model Intercept = 18.50
- model coeficient = 3.77
- **Equation**: Tokens = 18.50 + 3.77 * (Minutes Worked)
- **Example**: If 65 hours are worked in a month, the expected tokens earned are **14,723**.

### Prophet Model
- The Prophet model incorporates temporal features but performed slightly worse than the simple linear regression due to the small dataset size.

---

## Future Analysis
- The analysis was conducted using one year of historical data. With more data, predictions can be refined and extended to longer periods (e.g., bimonthly or quarterly).
- Additional features, such as audience engagement metrics, could improve the predictive model.

---