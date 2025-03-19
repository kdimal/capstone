
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
KMeans clustering identified 4 distinct customer segments based on purchase behavior (Total and Quantity). The segments range from high-value customers who make larger purchases with higher quantities, to low-frequency buyers who may make occasional, smaller purchases. Tailoring marketing messages and promotions to these segments will be key in improving engagement and driving sales.  These are the 4 key groups:
                          
    + Price sensitive customers - These are customers with low item count and low priced items.  We recommend focusing on promoting discounts, special offers, and clearance sales. Use coupon codes, limited-time deals, and loyalty programs to reward frequent shoppers who are looking for the best price.
    + Value Shoppers - These are customers with moderate item count (4-6) and moderately priced items.  We recommend emphasizing the balance between quality and price. Highlight bundle deals, value packs, or seasonal promotions that offer a little extra for a modest increase in spend. Clear communication of product benefits and durability can build trust with these customers.
    + Bulk Buyers - These are customers with high item count (8-10) with moderately priced items.  We recommend offering volume discounts and incentives for larger purchases. Consider loyalty programs that reward repeat bulk purchases, or create exclusive bulk-buy packages. Communication might include reminders for restocking and special pricing on multi-item purchases.
    + Hight Ticket/High Quantity Buyers (HTHQ) - These are customers with high item count and high priced items - note, big spenders.  We recommend developing a premium marketing approach with personalized service. Consider exclusive offers, early access to new products, and invitation-only events. Tailor loyalty rewards to reflect their significant spend, such as VIP customer programs or concierge-level service.

- Building on this, a further analysis was conducted using K-Prototypes, which incorporated categorical features—specifically, Gender and Product line—alongside the continuous variables. This approach uncovered four additional clusters that describe customer segments based on a combination of their demographic profile and product preferences. The gender–product line clusters offer a deeper understanding of how preferences vary among customer groups, such as differences in product interest between male and female customers, which can be leveraged to design more personalized and appealing marketing campaigns.

  + Female – Sports and Travel: These customers are active, adventurous women who enjoy sports and travel. They seek products that support a healthy, on-the-go lifestyle and value both performance and style in their gear.  We recommend the following marketing campaigns to this customer segment:  Feature product bundles that include travel-friendly sportswear, accessories, and fitness gear. Collaborate with influencers or athletes to share stories of travel and outdoor adventures. Offer seasonal promotions tied to travel periods (e.g., summer vacation deals or winter sports discounts). Introduce loyalty rewards for repeated purchases that emphasize a lifestyle of adventure and fitness.
  + Male – Electronic Accessories: These customers consist of tech-savvy men who prioritize functionality and innovation in their electronic accessories. They are early adopters who look for the latest gadgets to complement their digital lifestyles.  Recommended marketing campaigns:  Highlight new and innovative products through online demos, tech reviews, and unboxing videos.  Offer exclusive online promotions, bundle deals, or early-access offers for the latest releases. Run email and social media campaigns that showcase how these accessories seamlessly integrate with their existing tech setups. Consider partnering with tech influencers to provide authentic endorsements and reviews.
  + Male – Fashion Accessories:  These customers are style-conscious men who appreciate refined and trendy fashion accessories. They seek products that add a sophisticated touch to their everyday look, from watches to wallets and beyond.  Recommended marketing campaigns: Launch a curated collection of premium, limited-edition fashion accessories.  Use high-quality visuals and lookbooks that show the accessories in everyday and formal settings. Engage with fashion bloggers and stylists for endorsement and style tips. Offer personalized styling advice or exclusive membership programs that reward repeat purchases with discounts, previews, or bespoke services.
  + Female – Food and Beverages:  This group includes women who are passionate about culinary experiences and healthy living. They are interested in gourmet, organic, or innovative food and beverage products that can enhance their lifestyle.  We recommend the following campaigns: Develop content around recipes, cooking tips, and nutritional advice featuring your products. Run social media contests that encourage customers to share their favorite food experiences. Create subscription boxes or bundled deals that offer a curated taste experience, possibly highlighting seasonal or local products. Collaborate with food influencers, chefs, or nutritionists to build credibility and offer exclusive product insights.

