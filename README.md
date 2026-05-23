# Customer-Segmentation-Analysis
Project Overview
This project aims to understand customer behavior and identify distinct customer segments using a dataset containing various demographic and spending information. By segmenting customers, businesses can tailor marketing strategies, product offerings, and customer service to better meet the needs of each group.

Data Preparation and Cleaning
Data Loading: The customer_segmentation.csv dataset was loaded into a pandas DataFrame.
Date Conversion: The Dt_Customer column was converted to datetime objects.
Missing Values: Missing values in the 'Income' column were imputed using the mean income.
Age Calculation: Customer age was calculated from the Year_Birth column.
New Features: A 'Children' feature was created by summing Kidhome and Teenhome. A 'Spending' feature was created by summing all Mnt (amount spent) columns.
Exploratory Data Analysis (EDA)
Key insights from the EDA include:

Income Distribution: The income distribution shows a wide range, with a concentration in the middle-income brackets, and some high-income outliers.
Age Distribution: The customer base is diverse in age, with a notable presence of middle-aged and older customers.
Education and Marital Status: The dataset includes customers from various educational backgrounds and marital statuses, with 'Graduation' being the most common education level.
Income vs. Age: A scatter plot revealed that income generally increases with age up to a certain point, with some high-income earners across different age groups. Education and marital status also show patterns within these relationships.
Spending Habits: Significant spending is observed across several product categories, particularly 'MntWines' and 'MntMeatProducts'. There's considerable variation in spending across different educational levels and marital statuses.
Impact of Children: The number of children in a household shows a negative correlation with spending on most product categories, particularly wines and meat products, and also with income.
Campaign Effectiveness: Campaigns show varying degrees of success, with 'Response' (last campaign acceptance) and 'AcceptedCmp5' showing higher percentage contributions to total spending. 'AcceptedCmp5' also had the highest correlation with wine spending.
Customer Segmentation using K-Means Clustering
Objective
The goal was to group customers into distinct segments based on their demographic and spending patterns to enable targeted marketing efforts.

Methodology
Feature Selection: Irrelevant columns (ID, Year_Birth, Dt_Customer, Z_CostContact, Z_Revenue, and individual campaign response columns) were dropped.
One-Hot Encoding: Categorical features like 'Education' and 'Marital_Status' were converted into numerical format using one-hot encoding.
Feature Scaling: Numerical features were scaled using StandardScaler to ensure that all features contribute equally to the clustering process.
Optimal K Determination: The Elbow method was used to determine the optimal number of clusters. The plot of Within-Cluster Sum of Squares (WCSS) suggested K=4 as the optimal number of clusters.
K-Means Application: A K-Means model with 4 clusters was fitted to the scaled data, and cluster labels were assigned to each customer in the original DataFrame.
Cluster Analysis and Interpretation
Cluster 0 (High Spenders, Mid-High Income, Older)

Income: Mid-High income group.
Age: Generally older customers.
Children: Moderate number of children.
Spending: High spending across most categories, especially wines and meat products. High total spending.
Characteristics: Likely established households, potentially empty-nesters, with significant disposable income.
Cluster 1 (Low Spenders, Low Income, Younger)

Income: Lowest income group.
Age: Younger customers.
Children: Higher number of children.
Spending: Very low spending across all product categories. Low total spending.
Characteristics: Likely younger families with limited disposable income, prioritizing basic needs.
Cluster 2 (Very High Spenders, High Income, Mid-Age)

Income: Highest income group.
Age: Mid-age customers.
Children: Very few children.
Spending: Extremely high spending across all categories, particularly wines and meat products. Highest total spending.
Characteristics: Affluent individuals or couples, possibly without children at home, who are premium product consumers.
Cluster 3 (Moderate Spenders, Mid-Low Income, Diverse Age)

Income: Mid-low income group.
Age: Diverse age range.
Children: Highest number of children.
Spending: Moderate spending, generally higher than Cluster 1 but significantly lower than Clusters 0 and 2.
Characteristics: Likely larger families, balancing budget with product consumption. They might be value-conscious.
Cluster Distribution
The countplot shows the number of customers in each cluster, indicating the relative size of each segment.

Spending Distribution Across Clusters
The boxplot of total spending across clusters visually confirms the distinct spending patterns identified in the quantitative summary, with Cluster 2 having the highest median and spread of spending, and Cluster 1 the lowest.

Conclusion and Recommendations
This customer segmentation provides a clear framework for developing targeted marketing strategies:

For Cluster 2 (Very High Spenders): Focus on premium product offerings, exclusive deals, and personalized experiences. They are likely receptive to luxury items and high-value propositions.
For Cluster 0 (High Spenders): Target with quality products and loyalty programs. They have strong purchasing power and are valuable customers.
For Cluster 3 (Moderate Spenders): Offer family-sized products, bundles, and value-oriented promotions. Emphasize practicality and budget-friendliness.
For Cluster 1 (Low Spenders): Focus on essential goods, discounts, and entry-level products. Consider strategies to convert them to higher-tier segments over time, perhaps by highlighting value.
By leveraging these insights, businesses can optimize their marketing spend, improve customer satisfaction, and drive higher engagement and sales.
