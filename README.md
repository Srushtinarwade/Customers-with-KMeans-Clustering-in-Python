# Customers-with-KMeans-Clustering-in-Python

## Project Overview
This project focuses on customer segmentation using the **Online Retail** dataset. The goal is to group customers into distinct clusters based on their purchasing behavior using **K-Means Clustering**. By analyzing metrics such as Recency, Frequency, and Monetary value (RFM), this project provides actionable insights that can be used for targeted marketing and customer relationship management.

## Dataset
The data used in this project is the `online_retail_II.xlsx` dataset, which contains transactional data of a UK-based registered non-store online retail business. 

### Data Attributes
- **Invoice**: Invoice number (A 6-digit integral number uniquely assigned to each transaction. If it starts with 'C', it indicates a cancellation).
- **StockCode**: Product/item code.
- **Description**: Product/item name.
- **Quantity**: The quantities of each product per transaction.
- **InvoiceDate**: Invoice Date and time.
- **Price**: Unit price.
- **Customer ID**: Customer number uniquely assigned to each customer.
- **Country**: The name of the country where each customer resides.

## Technologies Used
- **Python 3.x**
- **Pandas** (Data manipulation and analysis)
- **Matplotlib & Seaborn** (Data visualization)
- **Scikit-Learn** (Machine Learning: KMeans, StandardScaler, Silhouette Score)

## Methodology
The project pipeline is divided into the following key stages:

### 1. Data Exploration & Cleaning
- **Handling Missing Values:** Transactions with missing Customer IDs were dropped to ensure customer-centric analysis.
- **Filtering Anomalies:** - Excluded manual adjustments, postage fees (e.g., 'DOT', 'M', 'BANK CHARGES', 'AMAZONFEE').
  - Handled cancelled orders and bad debt adjustments (Invoices starting with 'C' or 'A').
  - Filtered out records with zero or negative prices and quantities.
- **Standardizing Formats:** Cleaned string formats and strictly filtered valid StockCodes.

### 2. Feature Engineering (RFM Analysis)
To accurately cluster customers, we computed the RFM metrics for each user:
- **Recency:** Number of days since the customer's last purchase.
- **Frequency:** Total number of transactions made by the customer.
- **Monetary:** Total spend by the customer.

### 3. Clustering
- Applied **StandardScaler** to normalize the RFM features, ensuring all metrics contribute equally to the distance calculations.
- Implemented **K-Means Clustering** to identify customer segments.
- Evaluated cluster quality using the **Silhouette Score**.

### 4. Evaluation and Visualization
- Analyzed the mean Recency, Frequency, and Monetary values for each cluster.
- Visualized the cluster distributions and average feature values using `matplotlib` and `seaborn` (e.g., dual-axis bar and line plots).

## Results
The clustering model successfully partitioned the customer base into distinct groups with shared behavioral traits (e.g., high-value loyal customers, churn-risk customers, and low-frequency buyers). The insights derived from these clusters can help tailor specific promotional campaigns and marketing strategies for different customer profiles.
