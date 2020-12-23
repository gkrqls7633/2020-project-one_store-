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

![data table](https://user-images.githubusercontent.com/68583172/103009171-a5cd8100-4579-11eb-8444-418efde43e68.PNG)

[Convert to Customer Table]

![image](https://user-images.githubusercontent.com/68583172/103009120-85052b80-4579-11eb-8798-475ceae91ac8.png)

### Data Preprocessing
[Remove Buyer of Information Disagreement]
- If a customer uses multiple payment methods when purchasing a product, one record will be generated for each payment method, which will be combined.

![image](https://user-images.githubusercontent.com/68583172/103010377-95b6a100-457b-11eb-8e7e-fafc23c9e4c6.png)

[Processing disagreement buyers who provide personal information]

![image](https://user-images.githubusercontent.com/68583172/103010684-08c01780-457c-11eb-8ffb-903a9eda7965.png)


* Customer Based Table
* Generate various derivatives
- Finally customer_data table shape : (85314, 29)

![customer table](https://user-images.githubusercontent.com/68583172/103008544-a6194c80-4578-11eb-8393-e1f91eee92ed.PNG)

[Log transformation]
- All of the numeric features have long tail shape
- Decrease the distortion of the graph after log transformation

![image](https://user-images.githubusercontent.com/68583172/103011186-d9f67100-457c-11eb-84d0-8309a8027526.png)

[Consumer Lifetime visualization]
- Create Derived variable : 'Frequency', 'Recency', 'T'
- Frequency : Frequency of transactions: How often did customers buy our products?
- Recency : Transaction recentity: How recently did the customer purchase?
- T : Last Unpurchased Period

![image](https://user-images.githubusercontent.com/68583172/103011640-9cdeae80-457d-11eb-8b8f-6ff2635d0909.png)

[Check skewness & Log transformation of Frequency]

![image](https://user-images.githubusercontent.com/68583172/103011709-b7b12300-457d-11eb-8f88-f94a31366ffa.png)

[K-means clustering using 'Frequency', 'Recency', 'T]
- Analysis of silhouette coefficients
- Maximum silhouette coefficient with 3 

![image](https://user-images.githubusercontent.com/68583172/103011997-3a39e280-457e-11eb-87c3-5713cb8e3beb.png)


[Encoding]
- Label Encoding : pref_tm(시간대), sex_clsf_cd(성별) 
- One-hot Encoding : pref_category(카테고리), mno_cd(통신사), Cluster_lkabel(고객 클러스터)

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


