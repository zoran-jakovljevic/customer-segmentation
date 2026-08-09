# 👥 Customer Segmentation

Machine Learning project for segmenting customers based on their demographic characteristics, purchasing behavior, and engagement with different sales channels.

---

## 📌 Project Overview

The goal of this project is to identify distinct customer segments based on customer demographics, purchasing behavior, and interaction with the company's sales channels.

The project covers the complete unsupervised Machine Learning workflow:

- Data loading
- Exploratory Data Analysis (EDA)
- Missing value handling
- Data cleaning
- Feature Engineering
- Correlation Analysis
- Data Transformation
- Feature Scaling
- K-Means Clustering
- Cluster Analysis
- PCA Dimensionality Reduction
- Customer Segment Interpretation
- Cluster Visualization

---

## 📂 Dataset

The project uses a customer marketing dataset containing information about customer demographics, purchasing behavior, campaign responses, and shopping activity.

The dataset contains **2,240 customers and 29 original features**.

### Main Features

#### Customer Demographics
- `Year_Birth`
- `Education`
- `Marital_Status`
- `Income`
- `Kidhome`
- `Teenhome`

#### Customer Activity
- `Dt_Customer`
- `Recency`

#### Product Spending
- `MntWines`
- `MntFruits`
- `MntMeatProducts`
- `MntFishProducts`
- `MntSweetProducts`
- `MntGoldProds`

#### Purchase Channels
- `NumWebPurchases`
- `NumCatalogPurchases`
- `NumStorePurchases`
- `NumDealsPurchases`
- `NumWebVisitsMonth`

#### Campaign Response
- `AcceptedCmp1`
- `AcceptedCmp2`
- `AcceptedCmp3`
- `AcceptedCmp4`
- `AcceptedCmp5`
- `Response`
- `Complain`

---

## ⚙️ Data Preprocessing

The following preprocessing steps were applied:

- Missing `Income` values were identified and imputed using the median income within the corresponding `Education` and `Marital_Status` groups.
- `Dt_Customer` was converted to a datetime format.
- Customer age was derived from `Year_Birth`.
- `Total_spending` was created by aggregating spending across all product categories.
- `Total_children` was created by combining `Kidhome` and `Teenhome`.
- `Customer_since` was created to represent the number of days since the customer joined the company.
- Additional customer-level features were analyzed to better understand purchasing and engagement behavior.

---

## 📊 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand:

- Customer income distribution
- Age distribution
- Spending behavior
- Purchasing activity across different channels
- Customer recency
- Relationships between demographic and behavioral variables
- Potential outliers
- Correlations between numerical features

Various visualizations were created using Matplotlib and Seaborn, including:

- Histograms
- Boxplots
- Scatterplots
- Correlation heatmaps
- Bar charts

---

## 🧩 Feature Selection

The following features were selected for customer segmentation:

- `age`
- `Income`
- `Total_spending`
- `NumWebPurchases`
- `NumStorePurchases`
- `NumWebVisitsMonth`
- `Recency`

These features were selected to represent different aspects of customer behavior, including:

- Demographic characteristics
- Customer purchasing power
- Overall spending
- Online purchasing activity
- In-store purchasing activity
- Website engagement
- Customer recency

---

## 📏 Feature Scaling

Since K-Means is a distance-based algorithm, the selected features were standardized before clustering.

`StandardScaler` was used to transform the features so that they have comparable scales and no individual feature dominates the clustering process because of its magnitude.

---

## 🤖 K-Means Clustering

K-Means clustering was used to divide customers into distinct groups based on similarities in their demographic and behavioral characteristics.

Different numbers of clusters were evaluated using the **Within-Cluster Sum of Squares (WCSS)** and the Elbow Method.

The final model was configured with **6 customer clusters**.

---

## 👥 Customer Segments

The resulting clusters were analyzed based on their average demographic and behavioral characteristics.

The following business-oriented descriptions were assigned to the clusters:

| Cluster | Description |
|--------:|-------------|
| 0 | Low-Spending Customers |
| 1 | Older Low-Spending Customers |
| 2 | High-Spending Customers |
| 3 | Premium Customers |
| 4 | Low-Spending Customers - Segment 2 |
| 5 | Affluent Older Customers |

The cluster descriptions are based on the average age, income, total spending, purchase activity, website visits, and recency of customers within each cluster.

---

## 🔎 Cluster Analysis

The customer segments show clear differences in purchasing behavior and customer characteristics.

### Low-Spending Customers

Customers with relatively low income and very low total spending.

### Older Low-Spending Customers

Older customers with relatively low spending and lower purchasing activity.

### High-Spending Customers

Customers with relatively high income and significantly higher spending compared with the low-spending segments.

### Premium Customers

The highest-income and highest-spending customer segment, with strong in-store purchasing activity and relatively low website visits.

### Low-Spending Customers - Segment 2

A second low-spending segment with similar income and spending levels to the first low-spending group, but different customer engagement and recency characteristics.

### Affluent Older Customers

Older customers with relatively high income and high spending, representing an important high-value customer segment.

---

## 📉 PCA Visualization

Principal Component Analysis (PCA) was applied to reduce the standardized feature space to two dimensions.

The first two principal components (`PCA1` and `PCA2`) were used to visualize the customer clusters in a two-dimensional space.

PCA was used for visualization purposes and not as the input for the K-Means clustering model.

---




