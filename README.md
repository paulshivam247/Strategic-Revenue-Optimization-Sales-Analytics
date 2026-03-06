# Sales Performance & Customer Intelligence Analysis

An end-to-end data analytics project that explores sales trends, customer behavior, cross-selling opportunities, and revenue forecasting using Python and machine learning.

## Business Problem

Businesses often struggle to understand how sales performance changes across products, customers, and regions. Without clear insights, it becomes difficult to:

- Identify high-value customers
- Optimize pricing strategies
- Improve cross-selling opportunities
- Predict future sales demand

This project analyzes historical sales data to uncover actionable insights and build predictive models for strategic decision making.

## Dataset

The dataset contains **2,823 order-line transactions** with **25 columns**.

Each row represents a **single product within an order**.

Key features include:

- Order Date
- Product Line
- Customer Name
- Country / City / Territory
- Quantity Ordered
- Price Each
- MSRP
- Deal Size
- Sales

## Project Workflow

1. Data Cleaning & Preprocessing
2. Exploratory Data Analysis
3. Time-Series Sales Analysis
4. Sales Forecasting
5. Market Basket Analysis
6. Customer Segmentation (RFM)
7. Pricing & Discount Analysis
8. Machine Learning Model
9. Operational Risk Assessment

## Key Insights

• Strong seasonal sales spikes occur in **Q4**, especially in **November**.

• Market basket analysis discovered strong cross-selling relationships between product lines, with lift values as high as **5.9**.

• Customer segmentation identified a small group of **high-value "Champion" customers driving a large portion of revenue**.

• Pricing analysis revealed **revenue leakage caused by excessive discounts** in certain product categories.

• Sales forecasting predicts **continued seasonal demand peaks**, allowing better inventory planning.

## Machine Learning Models

Two predictive models were developed:

### Sales Forecasting
- Model: Holt-Winters Exponential Smoothing
- Captures trend and seasonality
- Forecasts future monthly revenue

### Deal Size Classification
- Model: Random Forest Classifier
- Accuracy: 88.3%
- Most important feature: PriceEach (57%)

## Tech Stack

Python  
Pandas  
NumPy  
Matplotlib  
Scikit-learn  
Statsmodels  
Apriori Algorithm

## Project Structure

sales-analytics-project
│
├── data
│   └── sales_data_sample.csv
│
├── notebooks
│   └── Retail Store Sales & Customer Analytics (Exploratory + Predictive).ipynb
│
├── visuals
│   └── powerbi.pbix (Coming Soon)
│
└── README.md

## How to Run

1. Clone the repository

git clone https://github.com/yourusername/sales-analytics-project

2. Install dependencies

pip install -r requirements.txt

3. Run the notebook

jupyter notebook

## Future Improvements

• Deploy forecasting model into a dashboard  
• Add customer lifetime value (CLV) modeling  
• Build an interactive Power BI dashboard  
• Implement automated reporting pipeline

## 👤 Author

**Shib Paul**

Sales Performance Analyst passionate about solving business problems using data analytics, machine learning, and visualization.

📧 Email: shibsankarpaul.analyst@gmail.com  

💼 LinkedIn: https://www.linkedin.com/in/shibsankarpaulanalyst/

📊 Project Presentation: https://youtu.be/QXCYoVx5e9k
