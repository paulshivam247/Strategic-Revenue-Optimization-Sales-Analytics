Sales Performance & Customer Intelligence Analysis

Project Objective

The goal of this project is to analyze sales performance across products, countries, customers, and time to uncover strategic insights and predict future outcomes.

The analysis integrates:

Data cleaning & enrichment

Time-series analysis

Sales forecasting

Market basket analysis

Customer segmentation (RFM)

Machine learning models

🔹 Step 1: Data Loading & Initial Inspection
Environment Setup

Imported essential Python libraries:

pandas

numpy

matplotlib

sklearn

statsmodels

Handling Encoding

The dataset sales_data_sample.csv was loaded using:

encoding='latin1'

This resolves decoding errors common in transactional datasets.

Structural Review

Dataset size: 2,823 rows × 25 columns

Data granularity: Order-line level

Each row represents a single product within an order, not the full order.

🔹 Step 2: Comprehensive Data Cleaning
Fixing "NA" Interpretation

The value "NA" (North America) was incorrectly interpreted as a null value in the TERRITORY column.

This was corrected to preserve geographic data.

Text Standardization

Removed extra whitespace from:

CITY

STATE

Geographic Enrichment

Several improvements were applied:

Standardized state names

Example: "NY" → "New York"

Corrected city spelling inconsistencies

Filled 1,486 missing STATE values

Mapping logic used:

CITY + COUNTRY → STATE
Territory Integrity

Territory mapping was standardized to avoid duplication.

Example:

Ensured Singapore consistently maps to the same territory to prevent revenue duplication.

🔹 Step 3: Time-Series Transformation
Datetime Conversion

The ORDERDATE column was converted from object format to datetime format.

Growth Metrics Calculated

Month-on-Month (MoM)

Quarter-on-Quarter (QoQ)

Year-over-Year (YoY)

Like-for-Like Growth

Since 2005 contains partial-year data, growth calculations were adjusted to ensure fair comparison with full years.

🔹 Step 4: Sales Forecasting
Model Used

Holt-Winters Exponential Smoothing from statsmodels.

Model Configuration

Trend: Additive

Seasonality: Multiplicative

Seasonal period: 12 months

Forecast Insight

The model identifies strong seasonal demand.

Example:

November 2005 forecast revenue > $1.7M

🔹 Step 5: Market Basket Analysis
Data Preparation

Created a binary basket matrix:

Order Number × Product Line

Each cell indicates whether the product line appeared in the order.

Algorithm Used

Apriori Algorithm

Minimum Support: 5%

Metrics Calculated

Support

Confidence

Lift

Key Insight

Strong product affinity discovered:

Classic Cars + Ships → Vintage Cars + Trains
Lift = 5.9x

Customers buying these items are 5.9× more likely to purchase the associated products.

Revenue Uplift Simulation

Simulated 10% cross-sell conversion improvement.

Estimated Total Revenue Uplift: 4.33%

🔹 Step 6: Customer Intelligence (RFM Analysis)
Metrics Calculated

For 92 customers:

Recency – Days since last purchase

Frequency – Total unique orders

Monetary – Total customer spending

Customer Segmentation

Customers were grouped into:

Champions

Potential Loyalists

At Risk

Lost

Churn Prediction

A Logistic Regression model was built to estimate customer churn probability using RFM scores.

🔹 Step 7: Pricing & Margin Analysis
Discount Calculation
Discount % = (MSRP − PriceEach) / MSRP
Elasticity Analysis

Correlation analysis was performed between:

Discount levels

Quantity ordered

This helps evaluate price sensitivity.

Revenue Leakage Simulation

Analysis found revenue leakage in the Classic Cars product line.

Simulation showed:

Reducing discounts by 5% could significantly improve margins.

🔹 Step 8: Machine Learning – Deal Size Classification
Algorithm

Random Forest Classifier

Target Variable
DEALSIZE (Small, Medium, Large)
Preprocessing

Label Encoding for categorical variables

Train-test split

Model Performance

Accuracy: 88.3%

Feature Importance

Most influential feature:

PRICEEACH → 57% importance

Deal size is primarily driven by product pricing.

🔹 Step 9: Operational Risk Assessment
Order Success Rate
Order Success Rate = 94.46%

Calculated by excluding non-fulfilled order statuses.

Revenue at Risk

Orders with status:

On Hold

In Process

represent potential revenue risk.

Total Revenue at Risk: $323,709
📈 Key Business Outcomes

This analysis enables businesses to:

Improve cross-selling strategies

Forecast future sales demand

Identify high-value customers

Optimize pricing strategies

Reduce operational revenue risk

Support data-driven decision making

🛠️ Tools & Technologies

Python

Pandas

NumPy

Matplotlib

Scikit-learn

Statsmodels

Apriori Algorithm
