
# 🛒 Quick Commerce Data Analysis with Python

## 📌 Project Overview

This project analyzes a synthetic Quick Commerce (Q-Commerce) dataset containing **1 million order records** from platforms such as Blinkit, Zepto, Swiggy Instamart, Big Basket, and others.

The analysis focuses on revenue performance, average order value, customer satisfaction, delivery efficiency, product preferences, and discount impact using Python and exploratory data analysis (EDA).

The objective is to transform raw order data into meaningful business insights that can support data-driven decision-making.

## 🎯 Business Objectives

- Identify the platform generating the highest total revenue.
- Compare average order value across Q-Commerce platforms.
- Analyze customer ratings and satisfaction.
- Investigate the relationship between delivery time and delivery partner ratings.
- Identify popular product categories for specific customer segments.
- Evaluate the relationship between discounts, order value, and items per order.
- Compare platform operational efficiency using order volume and delivery time.

## 📂 Dataset Description

The dataset, `quick_commerce_data_raw.csv`, contains order-level information.

| Column | Description |
|---|---|
| Order_ID | Unique order identifier |
| Company | Quick Commerce platform |
| City | Customer's city |
| Customer_Age | Customer age |
| Order_Value | Total order value |
| Delivery_Time_Min | Delivery time in minutes |
| Distance_Km | Delivery distance in kilometres |
| Items_Count | Number of items in the order |
| Product_Category | Product category |
| Payment_Method | Payment method used |
| Customer_Rating | Customer satisfaction rating |
| Discount_Applied | Indicates whether a discount was applied |
| Delivery_Partner_Rating | Rating given to the delivery partner |

**Dataset size:** 1,000,000 rows and 13 columns.

*Note: This is a synthetic dataset created for data analysis and learning purposes.*

## 🛠️ Tools and Technologies

- **Python** – Data analysis and manipulation
- **Pandas** – Data cleaning, transformation, and aggregation
- **NumPy** – Numerical operations
- **Matplotlib** – Data visualization
- **Seaborn** – Statistical visualization
- **Plotly Express** – Interactive visualization exploration
- **Google Colab** – Notebook development and execution

## 🧹 Data Cleaning and Preprocessing

The following data preparation steps were performed:

1. Loaded the CSV dataset into a Pandas DataFrame.
2. Inspected column names, data types, summary statistics, and missing values.
3. Identified missing values in City, Items_Count, Customer_Rating, and Delivery_Partner_Rating.
4. Removed records with missing City values.
5. Filled missing Items_Count values using the mode.
6. Filled missing Customer_Rating values using company-level averages.
7. Filled missing Delivery_Partner_Rating values using delivery-time-group averages, followed by the overall mean for remaining missing values.
8. Examined numerical distributions using box plots.
9. Filtered out records with Order_Value greater than ₹2,500.
10. Converted Order_ID to a string and standardized selected numerical columns for analysis.

### Final Dataset

- **Initial records:** 1,000,000
- **Records after removing missing City values:** 948,000
- **Records after filtering Order_Value above ₹2,500:** 947,752
- **Final columns:** 13

## 📊 Exploratory Data Analysis and Business Questions

### 1. Which platform generates the highest total revenue?

Swiggy Instamart recorded the highest total order value in the analyzed dataset, while Jio Mart recorded the lowest.

| Platform | Total Order Value |
|---|---:|
| Swiggy Instamart | 76,353,684 |
| Blinkit | 72,445,450 |
| Zepto | 70,285,754 |
| Big Basket | 67,830,915 |
| Flipkart Minutes | 66,944,768 |
| Amazon Now | 65,778,875 |
| Dunzo | 63,953,734 |
| Jio Mart | 57,059,272 |

**Business insight:** Swiggy Instamart leads the platforms in total order value within this synthetic dataset.

*Note: The calculation sums Order_Value, so it represents total order value rather than verified company revenue or profit.*

### 2. Which platform has the highest average order value?

| Platform | Average Order Value |
|---|---:|
| Swiggy Instamart | 644.47 |
| Blinkit | 609.36 |
| Zepto | 592.80 |
| Big Basket | 574.61 |
| Flipkart Minutes | 562.73 |
| Amazon Now | 557.06 |
| Dunzo | 539.86 |
| Jio Mart | 482.46 |

**Business insight:** Swiggy Instamart has the highest average order value, while Jio Mart has the lowest.

### 3. How do customer ratings vary across platforms?

Average customer ratings from the analysis:

| Platform | Average Customer Rating |
|---|---:|
| Blinkit | 3.58 |
| Swiggy Instamart | 3.28 |
| Zepto | 3.20 |
| Big Basket | 3.10 |
| Flipkart Minutes | 3.02 |
| Amazon Now | 2.91 |
| Jio Mart | 2.82 |
| Dunzo | 2.43 |

**Business insight:** Blinkit has the highest average customer rating, while Dunzo has the lowest in the analyzed dataset.

Visualizations include box plots and rating-distribution comparisons.

### 4. Does delivery time affect delivery partner ratings?

- Average delivery time: approximately **16.51 minutes**.
- Average delivery partner rating: approximately **3.80**.
- Correlation between delivery time and delivery partner rating: approximately **-0.0028**.

**Business insight:** The calculated correlation is close to zero, indicating almost no linear relationship between delivery time and delivery partner ratings in this dataset.

This result does not establish that delivery time never affects customer experience; it describes the relationship measured in this analysis.

### 5. What is the most popular product category among Swiggy Instamart customers aged 30–39 in Mumbai?

The analysis filters records using:
- Company: Swiggy Instamart
- City: Mumbai
- Customer age: 30–39

| Product Category | Number of Orders |
|---|---:|
| Dairy | 368 |
| Fruits & Vegetables | 343 |
| Groceries | 341 |
| Household | 340 |
| Snacks | 329 |
| Personal Care | 305 |
| Beverages | 299 |

**Business insight:** Dairy is the most frequently ordered category for this specific customer segment.

### 6. Are discounts associated with higher order values or larger baskets?

| Discount Applied | Number of Orders | Average Order Value | Average Items per Order |
|---|---:|---:|---:|
| No | 567,906 | 475.97 | 10.31 |
| Yes | 379,846 | 711.73 | 10.32 |

**Business insight:** Orders with discounts have a higher average order value in this dataset, while the average number of items per order is nearly identical.

This is an association, not proof that discounts caused higher order values. Further analysis is needed to determine discount profitability and incremental order volume.

### 7. Which platform demonstrates strong operational efficiency?

| Platform | Total Orders | Average Delivery Time (Minutes) | Average Order Value |
|---|---:|---:|---:|
| Zepto | 118,565 | 9.64 | 592.80 |
| Dunzo | 118,463 | 14.18 | 539.86 |
| Blinkit | 118,887 | 15.12 | 609.36 |
| Swiggy Instamart | 118,475 | 16.07 | 644.47 |
| Flipkart Minutes | 118,965 | 17.05 | 562.73 |
| Big Basket | 118,047 | 18.03 | 574.61 |
| Amazon Now | 118,083 | 18.98 | 557.06 |
| Jio Mart | 118,267 | 23.01 | 482.46 |


## 👨‍💻 Author

**Aravind K**  
Data Analyst | MIS Reporting | Python | SQL | Power BI  
Bengaluru, India

- **GitHub:** [Aravind386](https://github.com/Aravind386)

