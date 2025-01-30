# Customer Personality Analysis and Clustering

This project aims to analyze customer personality traits and segment customers into distinct groups based on their purchasing behaviors and demographics. The analysis utilizes a dataset containing information about customer demographics, purchasing habits, campaign responses, and more. The project employs data preprocessing techniques, dimensionality reduction using PCA, and clustering using the Agglomerative Clustering algorithm to identify meaningful customer segments.

## Dataset

The dataset used in this analysis is the "Customer Personality Analysis" dataset, which can be found on Kaggle. It contains information about customers' demographics, purchasing behavior, and responses to marketing campaigns.

**Data Dictionary:**

| Attribute | Description |
|---|---|
| ID | Customer's unique identifier |
| Year_Birth | Customer's birth year |
| Education | Customer's education level |
| Marital_Status | Customer's marital status |
| Income | Customer's yearly household income |
| Kidhome | Number of children in customer's household |
| Teenhome | Number of teenagers in customer's household |
| Dt_Customer | Date of customer's enrollment with the company |
| Recency | Number of days since customer's last purchase |
| Complain | 1 if the customer complained in the last 2 years, 0 otherwise |
| MntWines | Amount spent on wine in the last 2 years |
| MntFruits | Amount spent on fruits in the last 2 years |
| MntMeatProducts | Amount spent on meat in the last 2 years |
| MntFishProducts | Amount spent on fish in the last 2 years |
| MntSweetProducts | Amount spent on sweets in the last 2 years |
| MntGoldProds | Amount spent on gold in the last 2 years |
| NumDealsPurchases | Number of purchases made with a discount |
| AcceptedCmp1 | 1 if customer accepted the offer in the 1st campaign, 0 otherwise |
| AcceptedCmp2 | 1 if customer accepted the offer in the 2nd campaign, 0 otherwise |
| AcceptedCmp3 | 1 if customer accepted the offer in the 3rd campaign, 0 otherwise |
| AcceptedCmp4 | 1 if customer accepted the offer in the 4th campaign, 0 otherwise |
| AcceptedCmp5 | 1 if customer accepted the offer in the 5th campaign, 0 otherwise |
| Response | 1 if customer accepted the offer in the last campaign, 0 otherwise |
| NumWebPurchases | Number of purchases made through the company's website |
| NumCatalogPurchases | Number of purchases made using a catalog |
| NumStorePurchases | Number of purchases made directly in stores |
| NumWebVisitsMonth | Number of visits to the company's website in the last month |


## Project Workflow

1. **Data Import and Exploration:**
   - Import the dataset using `pd.read_csv`.
   - Explore the data using descriptive statistics and visualizations to understand its structure and patterns.

2. **Data Preprocessing:**
   - Handle missing values in the 'Income' column using imputation.
   - Address inconsistencies in the 'Marital_Status' column.
   - Remove outliers in 'Year_Birth' and 'Income'.
   - Create new features: 
      - `Total_Accepted_Offers`: Sum of campaign responses.
      - `Age_Group`: Binned age categories.
      - `Income_Group`: Binned income categories.
      - `Family_Size`: Total number of kids.
      - `Has_Kids`: Binary indicator for having kids.
      - `Total_Spending`: Total spending across product categories.
      - `Customer_Tenure`: Categorized customer tenure based on enrollment date.
   - Encode categorical variables using Label Encoding.
   - Normalize numerical features using Min-Max scaling.

3. **Dimensionality Reduction:**
   - Apply Principal Component Analysis (PCA) to reduce the dimensionality of the dataset to 3 principal components.

4. **Clustering:**
   - Use the Elbow Method with Agglomerative Clustering to determine the optimal number of clusters.
   - Apply Agglomerative Clustering with the determined number of clusters to segment the customers.

5. **Evaluation and Insights:**
   - Analyze the characteristics of each cluster based on their demographics, purchasing behavior, and campaign responses.
   - Visualize the clusters using distribution plots and heatmaps.
   - Derive insights about customer segments to inform marketing strategies and business decisions.

## Results and Insights

The analysis identified 4 distinct customer segments with varying characteristics:

**Cluster 0: Low Acceptance, Low Spending**

* Budget-conscious, prioritizing essential spending.
* Low acceptance of offers.

**Cluster 1: Moderate Acceptance, High Spending**

* High disposable income, willing to spend.
* Selective about offers.

**Cluster 2: Moderate Acceptance, Low Spending**

* Loyal but financially constrained.
* Open to offers but selective.

**Cluster 3: High Acceptance, High Spending**

* Financially well-off, loyal, and highly responsive to offers.
* Key target for premium offerings.

These insights can be used to develop targeted marketing strategies for each segment, such as offering personalized promotions, tailoring product recommendations, and optimizing communication channels.

## Conclusion

This project demonstrates the application of data analysis and clustering techniques to understand customer personality and segment customers into meaningful groups. The insights gained from this analysis can be valuable for businesses to improve customer targeting, personalize marketing efforts, and enhance customer relationships.
