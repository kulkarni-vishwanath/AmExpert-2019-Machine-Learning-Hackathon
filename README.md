![amex](https://user-images.githubusercontent.com/25604111/68610721-627f9280-04de-11ea-9b04-e563d07c4a5b.jpg)

# Predicting Coupon Redemption

XYZ Credit Card company regularly helps it’s merchants understand their data better and take key business decisions accurately by providing machine learning and analytics consulting. ABC is an established Brick & Mortar retailer that frequently conducts marketing campaigns for its diverse product range. As a merchant of XYZ, they have sought XYZ to assist them in their discount marketing process using the power of machine learning. Can you wear the AmExpert hat and help out ABC?

Discount marketing and coupon usage are very widely used promotional techniques to attract new customers and to retain & reinforce loyalty of existing customers. The measurement of a consumer’s propensity towards coupon usage and the prediction of the redemption behaviour are crucial parameters in assessing the effectiveness of a marketing campaign.

ABC’s promotions are shared across various channels including email, notifications, etc. A number of these campaigns include coupon discounts that are offered for a specific product/range of products. The retailer would like the ability to predict whether customers redeem the coupons received across channels, which will enable the retailer’s marketing team to accurately design coupon construct, and develop more precise and targeted marketing strategies.

The data available in this problem contains the following information, including the details of a sample of campaigns and coupons used in previous campaigns -

#### User Demographic Details

#### Campaign and coupon Details

#### Product details

#### Previous transactions

<img width="848" alt="amex19" src="https://user-images.githubusercontent.com/25604111/68610794-9d81c600-04de-11ea-9fe6-444d143ea4ab.png">


Based on previous transaction & performance data from the last 18 campaigns, predict the probability for the next 10 campaigns in the test set for each coupon and customer combination, whether the customer will redeem the coupon or not?

## Evaluation Metric
Submissions are evaluated on area under the ROC curve between the predicted probability and the observed target.

## Approach to Problem Solving:
* The first and foremost step was to do some basic exploration of the datasets that were available that includes Missing value imputation, Outlier treatment etc. One main observation while carrying out EDA was that the dependent variable was highly imbalanced. This needed a different approach to Modelling. 
* The second step was to combine the datasets into a Train and a Test dataset.
* The next step was to create additional features from the Datetime variable available to us. Features such as Month, Day, Weekend etc. 
* I also created a few grouped features such as Mean, Median, Count etc Grouped by afew variables.
* Since the categorical variables cannot be used as is in the model, I used LabelEncoding to encode categorical features. 
* The next step was to remove the Highly correlated variables as they impart same information and it might lead to overfitting.
* Since the variables were in a different scale , I had to standardize them in order to bring all of them to same scale. 
* Since the datais highly imbalanced, I had to use a combination of Oversampling and Undersampling in order to balance the data. 
* For modelling, I used Stratified K Fold with Light GBM with class_weight='balanced' parameter in order to get the results. 

## Leaderboard

[Public LB] : 234rd/1021 Rank

[Private LB] : 207th/1021 Rank
