Customer Segmentation with KMeans Clustering:
Overview:
This project uses KMeans clustering to perform customer segmentation based on purchasing behavior. By analyzing Monetary Value, Frequency, and Recency (RFM metrics) of transactions, customers are grouped into segments to understand different behaviors and characteristics. The goal is to provide actionable insights that businesses can use to tailor their marketing, customer service, and retention strategies.

The dataset used in this project contains transaction records from an online retail store, which includes information on customer ID, transaction details (quantity, price, and total value), invoice dates, and more.
dataset link : https://docs.google.com/spreadsheets/d/1LsWDXkF4uHNNtqCHdPVj9Bm3Vqozy3Wi/edit?usp=drive_link&ouid=106909808790301394460&rtpof=true&sd=true

2. Required Libraries:
The project requires the following Python libraries:

pandas: Data manipulation and analysis.
numpy: Array operations and mathematical functions.
matplotlib: Visualization library for plotting graphs.
seaborn: Statistical data visualization.
scikit-learn: Machine learning library (used for KMeans clustering).
openpyxl: Reading/writing Excel files.

Data Preprocessing
1. Data Import and Exploration:
The dataset is read from an Excel file (online_retail_II.xlsx). Basic exploratory data analysis (EDA) is performed to check for missing values, data types, invalid entries, and outliers. The following cleaning steps are applied:

Removal of rows with missing Customer ID.
Filtering of invalid Invoice and StockCode formats.
Removal of rows with zero price.
Identification and removal of outliers based on the Monetary Value and Frequency of purchases.
The cleaned data is saved to a CSV file for further analysis.

2. RFM Features (Monetary Value, Frequency, and Recency):
The dataset is aggregated at the Customer ID level to calculate:

Monetary Value: Total value of a customer's purchases.
Frequency: The number of unique invoices a customer has.
Recency: The number of days since a customer's last purchase.
These features are used for customer segmentation through KMeans clustering.

KMeans Clustering
1. Data Standardization:
Before performing clustering, the features (Monetary Value, Frequency, and Recency) are standardized using StandardScaler from scikit-learn to ensure the data is on the same scale.

2. Optimal Number of Clusters:
The Elbow Method and Silhouette Score are used to determine the optimal number of clusters. The silhouette score helps in evaluating the consistency of clusters, and the elbow method looks for the "elbow point" in the inertia curve.

3. KMeans Clustering:
Once the optimal number of clusters is determined (in this case, 4), KMeans clustering is applied to the standardized data. The customers are grouped into 4 main clusters and additional outlier clusters.

4. Clusters:
Main Clusters:

Cluster 0 (Blue): "Retain": High-value, regular customers that require retention strategies.
Cluster 1 (Orange): "Re-Engage": Infrequent, low-value customers that need re-engagement.
Cluster 2 (Green): "Nurture": Recent, low-value customers that need nurturing.
Cluster 3 (Red): "Reward": High-value, frequent customers that should be rewarded for their loyalty.
Outlier Clusters:

Cluster -1 (Monetary Outliers): "Pamper": High spenders, low frequency buyers.
Cluster -2 (Frequency Outliers): "Upsell": Frequent, low-spending buyers.
Cluster -3 (Monetary & Frequency Outliers): "Delight": High spenders with frequent purchases (top-tier customers).
5. Visualizations:
Several visualizations are included to help understand the clusters, such as:

Histograms and boxplots for Monetary Value, Frequency, and Recency.
3D scatter plots to visualize customer behavior in relation to the three features.
Violin plots for visualizing the distribution of features by cluster.
Insights and Actions
Based on the clustering results, the project have identified several segments with specific strategies for engagement:

Cluster 0 (Blue): "Retain"

Action: Focus on retention strategies like loyalty programs and personalized offers.
Cluster 1 (Orange): "Re-Engage"

Action: Re-engage customers through targeted campaigns, discounts, or reminders.
Cluster 2 (Green): "Nurture"

Action: Nurture new or low-value customers with relationship-building efforts and incentives.
Cluster 3 (Red): "Reward"

Action: Reward loyal, high-value customers with exclusive offers and personalized experiences.
Outlier Clusters:
Cluster -1 (Pamper): High-spending but infrequent buyers. Action: Provide luxury offers and personalized attention.
Cluster -2 (Upsell): Frequent but lower-spending customers. Action: Upsell through bundling and loyalty programs.
Cluster -3 (Delight): Top-tier customers with both high frequency and high spend. Action: Offer VIP services and exclusive deals.

By applying KMeans clustering to customer behavior data, this project enables businesses to segment their customers effectively, identify high-value customers, and tailor their marketing efforts accordingly. The actionable insights derived from clustering help in improving customer retention, re-engagement, and overall satisfaction.

Important Insights
From the K-Means clustering, the project derived several insights and actionable strategies for each customer segment. The segmentation is divided into main clusters and outlier clusters based on customer behavior:

Main Clusters:
Cluster 0 (Blue): "Retain"
Rationale: This cluster represents high-value customers who purchase regularly, though not always very recently. These customers are loyal, but their frequency of purchase might be declining.
Action: Focus on retention efforts such as loyalty programs, personalized offers, and regular engagement to maintain their spending levels and prevent churn.

Cluster 1 (Orange): "Re-Engage"
Rationale: This group consists of lower-value, infrequent buyers who haven’t purchased recently. These customers may have drifted away but can still be won back.
Action: Use targeted marketing campaigns, special discounts, or reminders to bring them back into active purchasing behavior. Engage them with re-engagement strategies to drive repeat purchases.

Cluster 2 (Green): "Nurture"
Rationale: These customers are the least active and lowest-value, but they have made recent purchases, indicating they may be new or just need nurturing. They could become more valuable with the right strategies.
Action: Focus on relationship-building, offering excellent customer service, and providing incentives to encourage more frequent purchases and higher spending.

Cluster 3 (Red): "Reward"
Rationale: This cluster includes high-value, very frequent buyers, many of whom are still actively purchasing. These customers are your most loyal, and rewarding their loyalty is key to maintaining their engagement.
Action: Implement a robust loyalty program, provide exclusive offers, and recognize their loyalty with personalized rewards to keep them satisfied and loyal.

Outlier Clusters:

Cluster -1 (Monetary Outliers): "Pamper"
Rationale: High spenders but not necessarily frequent buyers. These customers make large purchases but do so infrequently. They are valuable when they do purchase, but their buying patterns are irregular.
Action: Focus on maintaining their loyalty with personalized offers or luxury services that cater to their high spending capacity. Exclusive, high-end products or tailored services can help increase their satisfaction and repeat purchases.

Cluster -2 (Frequency Outliers): "Upsell"
Rationale: Frequent buyers who spend less per purchase. These customers engage regularly, but their individual transactions are smaller in value. They are consistently engaged, which presents an opportunity for higher revenue per transaction.
Action: Implement loyalty programs or bundle deals to encourage higher spending per visit. Promote upselling opportunities, such as adding related items to their frequently purchased products, to increase their average transaction value.

Cluster -3 (Monetary & Frequency Outliers): "Delight"
Rationale: These are the most valuable outliers, with both extreme spending and frequent purchases. They are likely your top-tier customers who require special attention to ensure their continued loyalty and satisfaction.
Action: Develop VIP programs or exclusive offers for these high-priority customers to maintain their loyalty and encourage continued engagement. Personalized services, access to exclusive products, or early access to new collections could be part of a tailored strategy to retain and delight this group.
