# Optional Power BI Guide

The Python script creates `outputs/customers_with_clusters.csv` after you run it.

1. Open Power BI Desktop.
2. Select **Get data → Text/CSV** and import `outputs/customers_with_clusters.csv`.
3. In Power Query, confirm data types: CustomerID = whole number; Age = whole number; AnnualIncome_kUSD = whole number; SpendingScore = whole number; Cluster = whole number.
4. Select **Close & Apply**.
5. Add KPI cards:
   - Total customers: count of CustomerID
   - Average spending score: average of SpendingScore
   - Average annual income: average of AnnualIncome_kUSD
6. Add a scatter chart:
   - X-axis: AnnualIncome_kUSD
   - Y-axis: SpendingScore
   - Legend: Cluster
   - Details/Values: CustomerID (if available in your Power BI version)
7. Add a clustered column chart:
   - Axis: Cluster
   - Values: count of CustomerID
8. Add a table with Cluster, Age, AnnualIncome_kUSD, and SpendingScore averages. If you want exact cluster averages, import `outputs/cluster_summary.csv` as a second table.
9. Add slicers for Gender and Age if useful.
10. Suggested page title: **Customer Segmentation Dashboard**.

Note: Power BI visuals present the clusters; the Python script performs the K-Means clustering. The dataset is synthetic and for practice only.
