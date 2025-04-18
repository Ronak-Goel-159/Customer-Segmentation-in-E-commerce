# 🛍️ Customer Segmentation in E-Commerce using K-Means Clustering

This project focuses on segmenting customers based on their purchasing behavior in an e-commerce dataset. The objective is to identify distinct customer segments using unsupervised machine learning techniques, specifically K-Means Clustering. The project also incorporates data visualization techniques such as PCA (Principal Component Analysis) and heatmaps to help understand customer behavior patterns.

## 📊 Project Overview

**Objective:**  
The goal of this project is to segment customers into distinct groups that exhibit similar behavior. These segments can then be used for targeted marketing, personalized recommendations, and improving customer retention strategies. The clustering is based on the following key features:
- Total amount spent by each customer (`total_spent`)
- Total number of unique purchase invoices (`total_purchases`)
- Number of unique items purchased (`unique_items`)

By applying K-Means clustering, we aim to group customers with similar behaviors into clusters, which can later inform business strategies such as promotions, product recommendations, and personalized experiences.

---

## 🧠 Techniques Used

This project implements several key data science techniques:

### 1. **Data Cleaning & Feature Engineering**
   - **Data Cleaning:** The dataset is cleaned by filtering out rows where `Quantity` or `UnitPrice` is non-positive, as they represent invalid or irrelevant transactions.
   - **Feature Engineering:** We create a new feature `TotalPrice`, which is the product of `Quantity` and `UnitPrice`, representing the total transaction value for each purchase.

### 2. **Standardization (Scaling)**
   - We standardize the data using `StandardScaler` to ensure that each feature contributes equally to the clustering algorithm. This is crucial because K-Means clustering is sensitive to the scale of the features.

### 3. **K-Means Clustering**
   - We apply K-Means clustering with `n_clusters=4`, which means we attempt to segment customers into 4 distinct groups based on their behavior. The number of clusters is chosen as a starting point, but can be adjusted using techniques like the Elbow Method or Silhouette Score for optimal results.

### 4. **Principal Component Analysis (PCA)**
   - PCA is used for dimensionality reduction, reducing the dataset from multiple features to two principal components (PC1 and PC2). This allows for effective visualization of the high-dimensional customer data in 2D, which makes it easier to interpret the clusters.

### 5. **Data Visualization**
   - **PCA Scatter Plot:** We create a scatter plot of the first two principal components (PC1 and PC2) to visualize the clustering results. Each point is a customer, and different clusters are color-coded for easy identification.
   - **Heatmap:** A heatmap is generated to show the average behavior of each customer cluster across the key features (`total_spent`, `total_purchases`, `unique_items`), providing insights into the characteristics of each segment.

---

## 🧠 Features Used for Clustering

The following features are used to define the customer segments:

1. **`total_spent`**: The total amount spent by a customer across all their purchases.
2. **`total_purchases`**: The total number of unique invoices (i.e., distinct transactions) made by the customer.
3. **`unique_items`**: The total number of distinct items purchased by the customer.

These features help capture the spending behavior, purchase frequency, and diversity of products bought by customers, which are essential for identifying meaningful segments.

---

## 📁 File Structure

The project consists of the following files:

```bash
.
├── customer_segmentation.py      # Main script that implements the analysis
├── 9. Customer Segmentation in E-commerce.csv  # Input dataset (e-commerce transaction data)
├── clustered_customers.csv       # Output file with customer segmentation (optional)
└── README.md                     # Project documentation
