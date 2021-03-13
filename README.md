# 2020-project-one_store

## Project name : [Predict whether or not to purchase a flat rate system]

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
![image](https://user-images.githubusercontent.com/68583172/103011640-9cdeae80-457d-11eb-8b8f-6ff2635d0909.png)

[K-means clustering using 'Frequency', 'Recency', 'T]
- Analysis of silhouette coefficients
- Maximum silhouette coefficient with 3 

### Modeling
1. CatBoost
2. LGBM
3. Logistic_Regression
4. Random_Forest
![image](https://user-images.githubusercontent.com/68583172/103015242-673cc400-4583-11eb-8a7d-a1c25ca47eb1.png)

- Catboost accuracy : 0.8642
- LGBM accuracy : 0.8636
- LR accuracy : 0.8261
- RF accuracy : 0.8636

[Ensenble result]
- accuracy : 0.8628

![image](https://user-images.githubusercontent.com/68583172/103015314-8b000a00-4583-11eb-90bf-cf7cd1dbbced.png)


