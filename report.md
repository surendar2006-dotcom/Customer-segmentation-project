# Customer Segmentation Project Report

## 1. Abstract
Customer segmentation groups customers with similar characteristics so an organization can understand different needs and plan more relevant marketing. This project demonstrates K-Means clustering on customer age, annual income, and spending score. The output includes cluster labels, summary statistics, and visualizations. The included data is synthetic and is intended only for learning.

## 2. Problem Statement
Treating every customer as if they have the same needs can lead to ineffective marketing. The goal is to identify groups with similar demographic and spending patterns and summarize the characteristics of each group.

## 3. Objectives
- Prepare and validate a customer dataset.
- Apply K-Means clustering using Python and scikit-learn.
- Compare candidate cluster counts using an elbow curve.
- Visualize clusters and summarize their average characteristics.
- Suggest responsible, segment-based marketing actions.

## 4. Tools and Technologies
- Python
- pandas and NumPy for data handling
- scikit-learn for standardization and K-Means
- Matplotlib for charts
- Optional: Power BI for an interactive dashboard

## 5. Dataset
The project uses a generated dataset of 1,000 demonstration customers with CustomerID, Gender, Age, AnnualIncome_kUSD, and SpendingScore. AnnualIncome_kUSD is annual income expressed in thousands of US dollars. SpendingScore is a simulated score from 1 to 100. No real individual or company records are included.

## 6. Methodology
1. Load the CSV and check required columns and missing values.
2. Select Age, AnnualIncome_kUSD, and SpendingScore as clustering features.
3. Standardize features using StandardScaler so different scales do not dominate distance calculations.
4. Fit K-Means models for K values 2 through 8 and save an elbow curve.
5. Fit a five-cluster model for this prepared teaching dataset using a fixed random seed for reproducibility.
6. Export each customer's cluster assignment and a summary containing customer count, average age, average income, average spending score, and customer share.
7. Calculate a silhouette score and create an income-versus-spending scatter plot.

## 7. Evaluation
The elbow curve shows how within-cluster inertia changes as K increases. The silhouette score provides an additional estimate of how well separated the clusters are. Neither metric should be used alone: the final number of segments should also be understandable and useful for the business. Run `customer_segmentation.py` to generate the numerical metrics and output tables.

## 8. How to Interpret the Results
Cluster IDs are arbitrary and may change if the data or model settings change. Inspect `outputs/cluster_summary.csv` and the scatter plot to describe each cluster based on its averages. For example, groups with higher income and higher spending may be candidates for premium offers, while high-income customers with lower spending may respond to product education or carefully tested incentives. Avoid assigning a segment name based only on its numeric ID.

## 9. Business Recommendations
- Tailor offers to observed customer needs rather than sending the same campaign to everyone.
- Test campaign ideas on a small sample and measure conversion, repeat purchases, and customer satisfaction.
- Review segments periodically because spending behavior can change.
- Use aggregate patterns and avoid sensitive or unfair profiling.

## 10. Limitations
- The data is synthetic, so findings do not represent a real retailer or customer population.
- K-Means requires a chosen number of clusters and can be affected by outliers and feature selection.
- Standardization and the selected features influence the results.
- Demographic data alone cannot explain customer motivations.
- Clusters are patterns, not guaranteed business categories.

## 11. Conclusion
This project demonstrates a complete beginner workflow for customer segmentation: data validation, feature scaling, K-Means clustering, evaluation, visualization, and actionable interpretation. It can be adapted to a real, appropriately authorized dataset by replacing the sample CSV and re-evaluating the number of clusters.

## 12. References
- scikit-learn documentation, KMeans: https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html
- scikit-learn documentation, StandardScaler: https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html
- scikit-learn documentation, silhouette_score: https://scikit-learn.org/stable/modules/generated/sklearn.metrics.silhouette_score.html
- pandas documentation: https://pandas.pydata.org/docs/
