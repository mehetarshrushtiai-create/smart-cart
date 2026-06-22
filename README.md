🛒 SmartCart — Customer Segmentation

Unsupervised machine learning project that segments customers of a retail store based on their demographics, lifestyle, and spending behavior — helping businesses tailor marketing strategies to distinct customer groups.

problem Statement

Retail businesses often treat all customers the same, missing opportunities to personalize offers and campaigns. This project uses clustering techniques to identify meaningful customer segments from transactional and demographic data.

📂 Dataset

File: smartcart_customers.csv
📥 Source: Kaggle — add the exact dataset link here
Key raw features include:
Feature                 Description
Year_Birth              Customer's birth year
Income                  Annual household income
Kidhome/Teenhome         Numberofkids/teensathome
Dt_Customer               Date_customer_joined
MntWines,MntFruits,etc.     Amount spent on each product category
Marital_Status,Education     Demographic info


🔧 Project Workflow
1. Data Preprocessing
Filled missing Income values with the median
Removed extreme outliers (Age > 90, Income > 600,000)

2. Feature Engineering
Age — derived from Year_Birth
Customer_Tenure_Days — days since joining
Total_Spending — sum across all product categories
Total_Children — kids + teens combined
Education — simplified into 3 tiers: Undergraduate, Graduate, Postgraduate
Living_With — simplified Marital Status into Partner / Alone

3. Encoding & Scaling
One-Hot Encoding for categorical features (Education, Living_With)
Standard Scaling applied before clustering

4. Dimensionality Reduction
PCA reduced features to 3 components for visualization and clustering

5. Finding Optimal K
Elbow Method (WCSS) to find the knee point
Silhouette Score to validate cluster quality
Both methods visualized on a combined dual-axis plot

6. Clustering
K-Means Clustering (k=4)
Agglomerative Clustering (ward linkage, k=4)
Results visualized in 3D PCA space

7. Cluster Characterization
Scatter plots of Income vs Total Spending per cluster
Cluster-wise mean summary across all features


Visualizations
Pair plots of key features
Correlation heatmap
3D PCA scatter plot (before and after clustering)
Elbow curve + Silhouette score (combined plot)
Income vs Spending colored by cluster


🛠️ Tech Stack
Python
pandas, numpy — data manipulation
matplotlib, seaborn — visualization
scikit-learn — PCA, KMeans, Agglomerative Clustering, StandardScaler
kneed — automatic elbow detection

Getting Started
bash# Clone the repository
git clone https:https://github.com/mehetarshrushtiai-create/smart-cart.git
cd smartcart

# Install dependencies
pip install pandas matplotlib seaborn scikit-learn kneed

# Launch the notebook
jupyter notebook smartcart.ipynb


Make sure smartcart_customers.csv is in the same directory as the notebook (included in this repo).
