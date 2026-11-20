# Mall Customer Segmentation

This project uses machine learning to find different groups of shoppers in a mall based on their Annual Income and Spending Score.

## 📊 What Algorithms Are Used?
1. **K-Means Clustering:** Grouping customers into 5 clusters.
2. **DBSCAN Clustering:** Grouping customers by density, leaving out outliers as noise.

## 🏆 The Final Verdict
* **Winner:** **K-Means** (5 clusters).
* **Why?** Both models find very similar customer groups, but K-Means is simpler and assigns every single customer to a segment.

## 💾 Output Files
* `customer_segments.csv`: Customer list with cluster assignments.
* `clustering_results_summary.csv`: Performance summary table.
