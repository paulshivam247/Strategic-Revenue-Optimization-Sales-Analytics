Project Objective
The primary goal is to analyze sales performance across products, countries, customers, and time to identify strategic business insights and predict future outcomes.

Step 1: Data Loading & Initial Inspection
Environment Setup: Import essential libraries including pandas, numpy, matplotlib, and sklearn
.
Handling Encoding: Load the dataset (sales_data_sample.csv) using encoding='latin1' to resolve decoding errors common in transactional data
.
Structural Review: Inspect the dataset's shape (2,823 rows, 25 columns) and verify data types
. Note that the data is at the order-line level, meaning each row represents a single product within an order
.
Step 2: Comprehensive Data Cleaning
Fixing "NA" Interpretation: Resolve the "North America" error where pandas misinterprets the string "NA" as a null value in the TERRITORY column
.
Text Standardization: Strip extra whitespace from CITY and STATE columns
.
Geographic Enrichment:
Standardize state names (e.g., "NY" to "New York") and correct city spellings
.
Use Vectorized Mapping with a custom dictionary to fill 1,486 missing STATE values based on CITY and COUNTRY pairs
.
Territory Integrity: Standardize territory mapping (e.g., ensuring Singapore is mapped consistently to avoid revenue duplication)
.
Step 3: Time-Series Transformation
Datetime Conversion: Convert the ORDERDATE column from an object to a proper datetime format
.
Performance Metrics: Calculate Month-on-Month (MoM), Quarter-on-Quarter (QoQ), and Year-over-Year (YoY) growth rates
.
Strategic Logic: Implement "Like-for-Like" growth calculations to accurately compare 2005 (partial year) against previous full years
.
Step 4: Predictive Modeling – Sales Forecasting
Model Selection: Deploy the Holt-Winters Exponential Smoothing model from statsmodels
.
Configuration: Set the model to handle additive trends and multiplicative seasonality (12-month period)
.
Forecast Output: Predict monthly revenue for the upcoming period, identifying seasonal peaks (e.g., forecasting over $1.7M for November 2005)
.
Step 5: Market Basket Analysis (Association Rules)
Data Prep: Create a binary "basket" matrix indicating which product lines appeared in each order
.
Apriori Algorithm: Identify frequent itemsets with a minimum support threshold (e.g., 5%)
.
Rule Generation: Calculate Lift, Confidence, and Support to find strong product correlations, such as the 5.9x lift between Classic Cars/Ships and Trains/Vintage Cars
.
Uplift Simulation: Model a 10% conversion of missed cross-sell opportunities to estimate a potential 4.33% total revenue uplift
.
Step 6: Customer Intelligence (RFM Analysis)
Metric Calculation: Compute Recency (days since last order), Frequency (total unique orders), and Monetary (total spend) for each of the 92 customers
.
Segment Definition: Use percentile scoring to categorize customers into segments like Champions, Potential Loyalists, At Risk, and Lost
.
Churn Prediction: Build a Logistic Regression pipeline to calculate the probability of churn for every customer based on their RFM scores
.
Step 7: Pricing & Margin Analysis
Discount Modeling: Calculate the Discount_% relative to MSRP
.
Elasticity Check: Perform correlation analysis between discount levels and quantity ordered to determine pricing power
.
Leakage Simulation: Quantify the "revenue leakage" in the Classic Cars line and simulate the profit gain from a 5% reduction in average discounts
.
Step 8: Machine Learning – Deal Size Classification
Algorithm: Implement a Random Forest Classifier to predict the DEALSIZE (Small, Medium, Large).
.
Preprocessing: Use LabelEncoder for categorical variables and split data into training and test sets.
.
Evaluation: Analyze the model's 88.3% accuracy and assess Feature Importance, discovering that PRICEEACH is the primary driver of deal classification (57%).
.
Step 9: Operational Risk Assessment
Success Metrics: Calculate the Order Success Rate (94.46%) by filtering out non-fulfilled statuses.
.
Revenue Protection: Quantify "Revenue at Risk" ($323,709) by aggregating sales for orders currently "On Hold" or "In Process".
