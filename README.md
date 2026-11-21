# 🛍️ ASIKON Mall Customer Segmentation

**Team:** Asikon (CSE 12th Batch) | **Platform:** Google Colab | **Language:** Python

## 📋 Project Overview

A mall has thousands of shoppers, but they don't all behave the same way. Some earn a lot and spend a lot, some earn a lot but spend little, and so on. This project uses two clustering algorithms — **K-Means** and **DBSCAN** — to find these customer groups automatically, without any labels, and then compares their results.

## 📊 Dataset

- **Source:** [Kaggle — Mall Customers Dataset](https://www.kaggle.com/datasets/shwetabh123/mall-customers)
- **Records:** 200 customers
- **Features used for clustering:** Annual Income (k\$), Spending Score (1–100)
- **Additional features used for profiling:** Age, Gender

## 🚀 How to Run

1. Open `ASIKON_Mall_Customer_Segmentation.ipynb` in **Google Colab**
2. Click **Runtime → Run all**
3. The dataset downloads itself via `kagglehub` — no manual upload needed
4. All figures are saved to the `figures/` folder automatically

## 🔬 Algorithms Used

| Algorithm | Type | Key Idea |
|-----------|------|----------|
| **K-Means** | Centroid-based | Assigns each customer to the nearest of *k* centroids; we pick *k* using the Elbow Method and Silhouette Score |
| **DBSCAN** | Density-based | Finds crowded regions separated by empty space; does not need *k* in advance; marks isolated customers as noise |

## 📈 Key Results

| Metric | K-Means | DBSCAN |
|--------|---------|--------|
| **Clusters found** | 5 | 7 |
| **Noise points** | 0 (0%) | 11 (5.5%) |
| **Silhouette score** | 0.5547 (all points) | 0.5154 (non-noise only) |

**Verdict:** K-Means is more suitable for this dataset — both methods give usable segments, but K-Means wins on simplicity and because it assigns every customer to a segment.

### K-Means Cluster Profiles (k = 5)

| Cluster | Income Level | Spending Level | Customers | Description |
|---------|-------------|----------------|-----------|-------------|
| 0 | Average | Average | 81 | Typical mid-range customers |
| 1 | High | High | 39 | Premium shoppers |
| 2 | Low | High | 22 | Enthusiastic spenders |
| 3 | High | Low | 35 | Careful high earners |
| 4 | Low | Low | 23 | Budget-conscious customers |

## 📁 Project Structure

```
├── ASIKON_Mall_Customer_Segmentation.ipynb   # Main notebook (code + outputs)
├── README.md                                  # This file
├── customer_segments.csv                      # Output: customer data with cluster labels
├── clustering_results_summary.csv             # Output: summary of results
└── figures/                                   # Output: all generated figures (PNG)
    ├── fig01_dataset_overview.png
    ├── fig02_distributions.png
    ├── fig03_boxplots.png
    ├── fig04_feature_relationships.png
    ├── fig05_correlation_heatmap.png
    ├── fig06_scaling.png
    ├── fig07_elbow_silhouette.png
    ├── fig08_kmeans_clusters.png
    ├── fig09_k_distance.png
    ├── fig10_eps_effect.png
    ├── fig11_dbscan_clusters.png
    ├── fig12_side_by_side.png
    └── fig13_model_comparison.png
```

## 🔧 Reproducibility

- **Random seed:** `RANDOM_STATE = 42`
- **Data:** Downloaded automatically from Kaggle via `kagglehub`
- **Libraries:** pandas, NumPy, matplotlib, seaborn, scikit-learn (Colab defaults)

## ⚠️ Limitations

- Small dataset (200 records) from a single mall — findings may not generalize
- Only two features (Income, Spending Score) used for clustering
- Spending Score is a mall-assigned score, not actual purchase amounts
- No ground truth available — quality judged by silhouette score and visual checks
- DBSCAN is sensitive to `eps` and `min_samples` parameter choices

## 🔮 Future Work

- Add Age as a third clustering feature
- Try Hierarchical or Gaussian Mixture clustering
- Validate on a different dataset
- Build a simple app that assigns a new customer to a segment

## 📚 References

- Dataset: [Mall Customers Dataset (Kaggle)](https://www.kaggle.com/datasets/shwetabh123/mall-customers)
- [scikit-learn K-Means Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)
- [scikit-learn DBSCAN Documentation](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html)

---

*This project was completed as part of the CSE 12th Batch Machine Learning coursework.*
