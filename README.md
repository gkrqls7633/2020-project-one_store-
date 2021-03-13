# 2020-project-one_store

## Project name : [Predict whether or not to purchase a flat rate system]

### summary
- Under the theme of [Predicting whether to purchase a flat-rate system] to identify customer characteristics and utilize predictive models (organized by the Korea Data Industry Promotion Agency)

### index
1. Select a topic
2. EDA
3. Data Preprocessing
4. Modeling & Result
5. Expectation Effectiveness


#### Original Data Table
* Transaction data of 2020/02~2020/07
- data shape : (40131396, 14)

* Customer Based Table
- Finally customer_data table shape : (85314, 29)
![customer table](https://user-images.githubusercontent.com/68583172/103008544-a6194c80-4578-11eb-8393-e1f91eee92ed.PNG)

[Log transformation]
- All of the numeric features have long tail shape
- Decrease the distortion of the graph after log transformation

[Consumer Lifetime visualization]
- Create Derived variable : 'Frequency', 'Recency', 'T'
- Frequency : Frequency of transactions: How often did customers buy our products?
- Recency : Transaction recentity: How recently did the customer purchase?
- T : Last Unpurchased Period

[K-means clustering using 'Frequency', 'Recency', 'T]
- Analysis of silhouette coefficients
- Maximum silhouette coefficient with 3 

### Modeling analysis
1. CatBoost
2. LGBM
3. Logistic_Regression
4. Random_Forest

![image](https://user-images.githubusercontent.com/68583172/103015242-673cc400-4583-11eb-8a7d-a1c25ca47eb1.png)
