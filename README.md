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

#### Convert to Customer Table

![image](https://user-images.githubusercontent.com/68583172/103009120-85052b80-4579-11eb-8798-475ceae91ac8.png)

### Data Preprocessing
#### Remove Buyer of Information Disagreement
- If a customer uses multiple payment methods when purchasing a product, one record will be generated for each payment method, which will be combined.

![image](https://user-images.githubusercontent.com/68583172/103010377-95b6a100-457b-11eb-8e7e-fafc23c9e4c6.png)

#### Processing disagreement buyers who provide personal information

![image](https://user-images.githubusercontent.com/68583172/103010684-08c01780-457c-11eb-8ffb-903a9eda7965.png)


* Customer Based Table
* Generate various derivatives
- Finally customer_data table shape : (85314, 29)

![customer table](https://user-images.githubusercontent.com/68583172/103008544-a6194c80-4578-11eb-8393-e1f91eee92ed.PNG)

#### Log transformation
- All of the numeric features have long tail shape
- Decrease the distortion of the graph after log transformation

![image](https://user-images.githubusercontent.com/68583172/103011186-d9f67100-457c-11eb-84d0-8309a8027526.png)

#### Lifetime visualization
- Create Derived variable : 'Frequency', 'Recency', 'T'


### Modeling
1. CatBoost
2. LGBM
3. Logistic_Regression
4. Random_Forest

- Catboost accuracy : 0.8642
- LGBM accuracy : 0.8636
- LR accuracy : 0.8261
- RF accuracy : 0.8636

