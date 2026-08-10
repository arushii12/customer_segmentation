# Customer Segmentation & Revenue Analytics

## Project Overview

This project analyzes 500K+ online retail transactions to understand customer purchasing behavior and identify meaningful customer segments.

Using *RFM (Recency, Frequency, Monetary) analysis* and *K-Means clustering*, 4,300+ customers were grouped into four distinct segments based on their purchase recency, purchase frequency, and total spending.

The resulting segments were analyzed to understand their contribution to revenue and develop targeted customer retention and growth strategies.

---

## Business Objective

The objective of the project is to answer key business questions such as:

- Who are the most valuable customers?
- Which customers are at risk of becoming inactive?
- How much revenue does each customer segment contribute?
- Which customer groups should be prioritized for retention?
- How can marketing strategies be customized for different customer segments?

---

## Dataset

The project uses the *Online Retail Dataset* from the UCI Machine Learning Repository.

The dataset contains 500K+ transactions from an online retail business and includes information such as:

- Invoice number
- Product description
- Quantity purchased
- Invoice date
- Unit price
- Customer ID
- Country

After data cleaning and aggregation, the analysis resulted in approximately *4,300 unique customers*.

---

## Data Cleaning

Before customer segmentation, the transaction data was cleaned to improve the quality of the analysis.

The following steps were performed:

- Removed transactions with missing Customer IDs
- Removed cancelled transactions
- Removed records with non-positive quantities
- Removed records with non-positive unit prices
- Converted invoice dates into datetime format
- Created total transaction value using Quantity × Unit Price

---

## RFM Feature Engineering

Customer purchasing behavior was summarized using three RFM metrics:

### Recency
Number of days since the customer's most recent purchase.

Lower Recency indicates a more recently active customer.

### Frequency
Number of unique purchases made by the customer.

Higher Frequency indicates greater customer engagement.

### Monetary
Total amount spent by the customer.

Higher Monetary value indicates greater customer value.

The transaction-level dataset was therefore transformed into a customer-level dataset containing:

*CustomerID | Recency | Frequency | Monetary*

---

## Customer Segmentation

Since RFM variables have different scales, the features were standardized using *StandardScaler* before clustering.

The optimal number of clusters was evaluated using:

- *Elbow Method*
- *Silhouette Score*

K-Means clustering was then applied to the standardized RFM features to identify *four customer segments*.

---

## Customer Segments

The resulting clusters were interpreted based on their RFM characteristics and assigned business-friendly labels:

### Premium
Very recent, highly frequent, and exceptionally high-spending customers.

### Loyal / High-Value
Recent and frequent customers with high overall spending.

### Core / Regular
The largest customer group, consisting of regular customers with moderate purchasing activity.

### At Risk / Lapsed
Customers with low purchasing frequency and a long period since their last transaction.

---

## Key Insights

- *Loyal and Premium customers represent approximately 5% of the customer base but contribute around 48% of total revenue.*

- *Core / Regular customers form the largest segment*, accounting for approximately 70% of customers and around 47% of revenue.

- *At-Risk / Lapsed customers represent approximately 25% of customers but contribute only around 6% of total revenue.*

- Revenue is therefore highly concentrated among a relatively small group of high-value customers.

- The results highlight both a strong *retention opportunity among high-value customers* and a *reactivation opportunity among At-Risk customers*.

---

## Business Recommendations

### Premium Customers
- Prioritize retention
- Provide personalized services
- Offer exclusive benefits and premium loyalty rewards

### Loyal / High-Value Customers
- Strengthen loyalty programs
- Use personalized recommendations
- Explore cross-selling and upselling opportunities

### Core / Regular Customers
- Encourage higher purchase frequency
- Provide targeted offers and recommendations
- Develop strategies to move customers toward the Loyal segment

### At Risk / Lapsed Customers
- Run targeted reactivation campaigns
- Provide personalized discounts
- Use reminders and win-back offers

---

## Principal Component Analysis 

Principal Component Analysis (PCA) was used to reduce the three standardized RFM dimensions into two principal components.

This allowed the customer clusters identified by K-Means to be visualized on a two-dimensional scatter plot.

PCA was used for *visualization purposes*, while the actual clustering was performed using all three standardized RFM variables.

---

## Tableau Dashboard

An interactive Tableau dashboard was developed to communicate the segmentation results and business insights.

The dashboard analyzes:

- Customer distribution across segments
- Revenue contribution by segment
- Recency across customer segments
- Purchase frequency
- Customer monetary value
- Customer share vs. revenue share
- High-value and At-Risk customer groups

The dashboard helps translate the clustering results into actionable business insights.

---

## Project Workflow

*Raw Transaction Data*

↓

*Data Cleaning & Preprocessing*

↓

*RFM Feature Engineering*

↓

*Feature Standardization*

↓

*Elbow Method & Silhouette Analysis*

↓

*K-Means Clustering*

↓

*Cluster Profiling & Business Segmentation*

↓

*PCA Visualization*

↓

*Revenue & Customer Analysis*

↓

*Tableau Dashboard*

↓

*Business Recommendations*

---

## Tech Stack

- *Python*
- *Pandas*
- *NumPy*
- *Scikit-learn*
- *K-Means Clustering*
- *PCA*
- *Matplotlib*
- *Seaborn*
- *Tableau*
- *Google Colab*

---

## Repository Files

### customer_segmentation.ipynb
Complete Python notebook containing data cleaning, RFM analysis, clustering, visualization, and business recommendations.

### customer_segments.csv
Final customer-level dataset containing:

- CustomerID
- Recency
- Frequency
- Monetary
- Cluster
- Segment

---

## Key Project Outcome

The analysis demonstrates how customer transaction data can be converted into actionable business segments using machine learning.

A key finding was that *approximately 5% of Loyal and Premium customers contributed nearly 48% of total revenue*, highlighting the importance of targeted retention and customer-value strategies.

---

## Data Source

*UCI Machine Learning Repository — Online Retail Dataset*

Dataset page:
https://archive.ics.uci.edu/dataset/352/online+retail
