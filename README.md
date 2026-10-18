# Customer Segmentation Using Clustering Algorithms and Dimensionality Reduction 📊

## 📌 Project Overview

This project applies unsupervised machine learning techniques to identify customer segments based on their annual income and spending behavior. Using a mall customer dataset, the notebook explores customer characteristics, applies different clustering algorithms, and uses dimensionality reduction techniques to visualize patterns in the data.

The project focuses on understanding how clustering algorithms group similar customers and how these segments can support data-driven business decisions.

## 🎯 Objectives

- Explore and understand the mall customer dataset.
- Perform data inspection and preprocessing.
- Scale numerical features for clustering.
- Apply K-Means, Hierarchical Clustering, and DBSCAN algorithms.
- Determine a suitable number of clusters using the Elbow Method and Silhouette Score.
- Apply PCA and t-SNE for dimensionality reduction and visualization.
- Analyze customer segments and identify potential business opportunities.

## 📂 Dataset Description

The project uses a mall customer spending dataset containing **200 rows and 5 columns**.

The dataset includes the following features:

| Feature | Description |
|---|---|
| CustomerID | Unique identifier for each customer |
| Genre | Customer gender category as provided in the dataset |
| Age | Age of the customer |
| Annual Income (k$) | Annual income in thousands of dollars |
| Spending Score (1-100) | Customer spending score on a scale of 1 to 100 |

The main clustering analysis uses **Annual Income** and **Spending Score** to identify customer segments.

**Dataset source:** [Mall Customer Spending Dataset on GitHub](https://github.com/GeethaGunasekaran1/Dataset_rep)

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- SciPy
- Google Colab / Jupyter Notebook

## 🔍 Project Workflow

### 1. Data Exploration and Preprocessing

- Load the dataset from an Excel file.
- Inspect the dataset's dimensions, column names, data types, and sample records.
- Check for missing values.
- Rename selected columns for easier access.
- Select Annual Income and Spending Score for the primary clustering analysis.
- Apply MinMaxScaler to normalize the selected features.

### 2. K-Means Clustering

K-Means partitions customers into a predefined number of clusters based on feature similarity.

The notebook:

- Applies K-Means with five clusters.
- Visualizes customer groups using a scatter plot.
- Displays the cluster centers.
- Uses the Elbow Method to examine Within-Cluster Sum of Squares (WCSS).
- Uses the Silhouette Score to evaluate cluster separation.

The highest recorded Silhouette Score in the tested range occurred at **K = 5**, with a score of approximately **0.559**.

### 3. Hierarchical Clustering

Hierarchical Clustering groups customers using a hierarchy of relationships between data points.

The notebook:

- Uses the Ward linkage method.
- Constructs a linkage matrix.
- Visualizes the clustering hierarchy with a dendrogram.
- Applies `fcluster` to obtain cluster assignments.
- Compares the resulting segmentation with K-Means.

The executed notebook reports five clusters for its selected dendrogram distance threshold.

### 4. DBSCAN Clustering

DBSCAN (Density-Based Spatial Clustering of Applications with Noise) identifies groups based on the density of nearby data points.

The notebook:

- Standardizes the selected features.
- Applies DBSCAN using `eps=0.3` and `min_samples=3`.
- Visualizes the resulting cluster assignments.
- Examines the number of clusters and the customer distribution across groups.

The notebook reports nine non-noise clusters. DBSCAN can also label points as `-1`, indicating noise or outliers that do not belong to a sufficiently dense cluster.

### 5. Dimensionality Reduction

The project explores two dimensionality reduction techniques.

**Principal Component Analysis (PCA)**

- Applies PCA to CustomerID, Age, Annual Income, and Spending Score.
- Calculates cumulative explained variance.
- Selects the number of components needed to reach at least 95% cumulative explained variance.
- Transforms the original four-feature dataset into two principal components.

**t-Distributed Stochastic Neighbor Embedding (t-SNE)**

- Applies t-SNE to the same four selected features.
- Reduces the data to two dimensions.
- Visualizes the resulting representation to explore local patterns and similarities between observations.

Both techniques produce two-dimensional representations for visualization.

### 6. Cluster Analysis and Business Recommendations

The notebook examines the customer counts and average scaled feature values associated with DBSCAN cluster labels.

This analysis helps explore customer groups with different income and spending characteristics, including:

- Customers with relatively high spending scores.
- Customers with relatively low spending scores.
- Customers with different income levels.
- Potential outliers and customers that do not fit clearly into dense groups.

These patterns can help businesses explore customer targeting, promotional campaigns, and personalized marketing strategies.

## 📊 Key Findings

- The dataset contains 200 customer records and five original features.
- No missing values were reported during the initial data inspection.
- K-Means achieved its highest tested Silhouette Score at five clusters, approximately 0.559.
- The Elbow Method was used to examine changes in WCSS as the number of clusters increased.
- Hierarchical Clustering produced five clusters at the selected distance threshold in the executed notebook.
- DBSCAN identified density-based customer groups and noise points.
- PCA reduced the selected four-feature dataset to two components while meeting the notebook's 95% cumulative explained variance threshold.
- t-SNE provided another two-dimensional representation for exploring customer patterns.

**Note:** Cluster counts and visual interpretations depend on the algorithm parameters, feature scaling, and selected input features. The five-cluster result from K-Means should not be treated as the final result of every algorithm.

## 🚀 Potential Improvements

- Compare clustering results using additional numerical features, such as Age.
- Evaluate different DBSCAN values for `eps` and `min_samples`.
- Use a consistent and reproducible preprocessing pipeline.
- Compare cluster quality using Silhouette Score and other suitable clustering metrics.
- Improve cluster visualizations by displaying cluster centers and clear legends.
- Profile each cluster using original feature values to make the results easier to interpret.
- Compare PCA and t-SNE visualizations with the original feature space.
- Use more meaningful customer segment names based on verified cluster characteristics.
- Validate the usefulness of the segments before making business recommendations.

## 📁 Project Structure

```text
Customer-Segmentation/
│
├── Assignment_08_Clustering_.ipynb
└── README.md
```

## ▶️ How to Run

1. Clone or download this repository.
2. Open `Assignment_08_Clustering_.ipynb` in Google Colab or Jupyter Notebook.
3. Install the required Python libraries if they are not already available.
4. Run the notebook cells in order.
5. Ensure that the dataset URL is accessible or update the dataset path if necessary.
6. Review the clustering plots, evaluation scores, dimensionality reduction results, and cluster analysis.

## 📚 Learning Outcomes

Through this project, I practised:

- Exploratory data analysis
- Missing-value inspection and feature selection
- Numerical feature scaling
- K-Means clustering
- Hierarchical Clustering and dendrogram interpretation
- DBSCAN clustering and noise detection
- Elbow Method and Silhouette Score analysis
- Principal Component Analysis (PCA)
- t-SNE dimensionality reduction
- Customer segmentation and business-oriented interpretation

## 👨‍💻 Conclusion

This project demonstrates an end-to-end unsupervised machine learning workflow for customer segmentation. By applying K-Means, Hierarchical Clustering, and DBSCAN, the notebook explores different approaches to grouping customers according to their income and spending behavior.

The use of PCA and t-SNE provides additional ways to visualize high-dimensional data and investigate underlying patterns. Overall, the assignment provides practical experience in clustering, dimensionality reduction, model evaluation, and customer behavior analysis.
