
# Capstone Project: Customer Segmentation for Retail Marketing Strategy

## Project Overview
The goal of this project is to enhance the marketing strategy of a retail company by segmenting customers based on their purchasing behavior. The objective is to identify distinct customer groups, which can then be targeted with tailored promotions and product offerings, ultimately increasing customer satisfaction and driving sales growth.

### Problem Statement:
How can we identify distinct customer groups based on their purchasing behavior to tailor marketing strategies and improve sales?

## Data Used
The dataset used for this analysis is a transaction dataset from a retail store, which includes various attributes such as:
- **Customer Demographics**: Age, Gender, Customer Type (Member or Normal)
- **Transaction Details**: Product line, Quantity, Unit price, Total value, Payment method, Date, and Time of purchase
- **Customer Feedback**: Rating provided by the customer

For this exercise, the publicly available data, Supermarket Sales data from Kaggle was used.  https://www.kaggle.com/datasets/markmedhat/supermarket-sales

### Key Variables:
- **Invoice ID**: Unique transaction identifier
- **Branch**: Location of the store
- **City**: The city where the transaction occurred
- **Total**: Total transaction value
- **Quantity**: Number of items purchased
- **Rating**: Customer rating for the transaction
- **Payment**: Payment method used (Cash, Credit card, Ewallet)
- **Product Line**: Type of product purchased

## Data Cleaning and Preprocessing
- The dataset had no missing values, so no imputation was required.
- Categorical columns were retained for segmentation (such as Gender, Product Line, Payment method).
- Numerical features such as Total and Quantity were scaled using **StandardScaler** for consistency in clustering.

## Exploratory Data Analysis (EDA)
Several visualizations were created to understand the distribution and relationships between key variables:
- Distribution of **Total Transaction Value** and **Quantity Purchased**
- **Total vs. Quantity**: Positive correlation between the total transaction value and the quantity purchased.
- **Customer Ratings by Payment Method**: Customers using Ewallet tend to provide higher ratings.
- **Distribution by Product Line**: Some product lines like Health and Beauty had more transactions than others.

## Clustering Analysis
Two clustering methods were applied to identify customer segments based on purchasing behavior:

### 1. **K-Means Clustering**:
- The optimal number of clusters (K=4) was determined using the **Elbow Method**.
- A **Silhouette Score** of 0.44 was obtained, suggesting moderate separation between the clusters.
- K-means clustering provided 4 distinct customer segments based on Total and Quantity purchased.

### 2. **DBSCAN Clustering**:
- **DBSCAN** was applied with parameters **epsilon=0.5** and **min_samples=5**.
- No outliers were identified, as all transactions were assigned to clusters.
- DBSCAN identified groups with varying densities, providing a different perspective on customer segmentation.

## Deviations from Original Capstone Description:
- The **original description** suggested incorporating **demographic data** (such as age, gender, and location) for segmentation. While the dataset includes this data, only **Total** and **Quantity** were used for clustering in this analysis. This is due to the focus on purchasing behavior for clustering, and demographic features could be integrated later for more advanced segmentation.
- The original description mentioned using K-means and DBSCAN techniques, which were both implemented as per the instructions.
- The data did not include any features related to customer **website interactions** or **responses to previous marketing campaigns**, which were mentioned in the initial description. This was not addressed due to the nature of the available dataset.
- A **Silhouette Score** (not learned in this class, but have learned in other forums) was used.  It is a measure of how well-defined the clusters are, providing an evaluation of the quality of the clustering results. It ranges from -1 to +1, where:  +1 indicates that the data points are well clustered (i.e., points are very close to their own cluster, and far from other clusters). 0 means that the data points are on or very close to the decision boundary between two clusters, making it unclear whether they belong to one or the other.  -1 suggests that the data points may have been assigned to the wrong cluster (i.e., they are closer to a different cluster than their own).
        
- **KMEANS** and **DBSCAN** were not used for demographic segmentation, as both are used for numerical features.  Since demography is a categorical variable, other models will be utilized in a future version (TBD). 

## Conclusion
The analysis and clustering of customer transactions provide meaningful insights into customer behavior that can significantly enhance the retail company's marketing strategy. By focusing on the purchasing behavior (i.e., total spend and quantity purchased), customer segments have been identified that offer actionable opportunities for personalized marketing and product offerings.

**Key Findings**:

- Purchasing Behavior and Customer Preferences:
Total Transaction Value and Quantity Purchased are key indicators of customer spending patterns. Most customers tend to make purchases with a moderate quantity (between 5 to 8 items), leading to a fairly consistent total transaction value. However, a small subset of customers makes larger purchases, which could indicate high-value or frequent buyers.
This variance in transaction value provides an opportunity for the company to target high-value customers (those with larger transaction totals) with special offers, loyalty programs, or exclusive product lines.

- Payment Method and Customer Satisfaction:
Customers using Ewallet tend to provide higher ratings, indicating a positive relationship between the payment method and customer satisfaction. This may suggest that customers who use digital payment methods (which often require more trust and ease of use) are more likely to have a favorable experience. This insight could guide the marketing team to offer more incentives for Ewallet users, such as discounts or rewards.
In contrast, customers using Cash and Credit Cards show a broader range of satisfaction, which may imply the need for improved customer service or promotions targeting these payment methods.

- Product Preferences and Customer Segmentation:
The segmentation analysis revealed that certain product lines such as Health and Beauty and Electronic Accessories dominate the customer transactions. These product lines are likely driving higher sales, and marketing efforts could focus on increasing the visibility of these categories through targeted promotions.
On the other hand, product lines like Sports and Travel or Home and Lifestyle show fewer transactions, which could suggest the opportunity to cross-sell or offer targeted discounts to boost interest in these categories.

- Customer Segments for Targeted Marketing:
KMeans clustering identified 4 distinct customer segments based on purchase behavior (Total and Quantity). The segments range from high-value customers who make larger purchases with higher quantities, to low-frequency buyers who may make occasional, smaller purchases. Tailoring marketing messages and promotions to these segments will be key in improving engagement and driving sales.
With DBSCAN, we observed a denser clustering of customers, suggesting that some customer segments may have very specific preferences that could be further explored. This finding implies that a more nuanced marketing approach could be employed, especially for customers who do not fit into the typical purchasing patterns.

- Segmentation for Personalized Offers:
By understanding the distribution of customers across various clusters, marketing teams can personalize promotions based on purchase frequency and average spend. For example, for high-value customers, exclusive offers on new products or early access to sales events can be extended.
Customers in the low-frequency clusters could be targeted with re-engagement campaigns, offering discounts or loyalty rewards to encourage more frequent visits.
