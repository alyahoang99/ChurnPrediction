# ChurnPrediction

## The fundamentals of churn prediction 
We gather historical data about users who have left and those who continue to use the product to train a model for churn predictions work. We calculate features that might contain signals indicating whether a user will leave or stay. For example, potential features for marketplace could include: how long the user has been on the service, when they made their last purchase, when they last logged, what their last reviewed as, what is the latest item they viewed and so on. 

How the churn prediction model is used 
- after training, the model is applied to active users of the service
- for users with a high risk of churn, a budget can be allocated to maintain their loyalty through bonuses, discounts, push notifcations or other incentives.
- incentives are a necessary intervention to preven user churn
- it is important to ensure that the costs of intervention are less than the profit obtained form the retained users.

But there is a problem with this approach, not all departing users are engaged equally: 
- users who will leave in any case (no actions on your part will affect their decision)
- users who can be influenced but the cost of retention is higher than the future potential profit (such users can be retained, but it is every expensive and is not economically justified)
- users who can be influenced and keep the retention cost will be below future profits (such users can be retained, and it is economically beneficial)

If you want to retain users in your product, build a user retention system not based on churn prediction but on uplift modeling. 

## The fundamental of uplift modeling 

To train a model within the framework of uplift modeling, it is necessary to conduct the following A/B test: 
- a portion of active product users is randomly divided into two groups: test and control
- chosen retention mechanism (bonuses, discounts, special communication) is applied to all users in the test group
- the experience of users from the control group does not change

A/B test will enable us to collect data on how motivation and retention mechanisms affect user behavior and overall product metrics. 
consequently, we may observe that the retention mechanics: 
- do not work at all, in such case, there is no point in creating ML models, and it is necessary to investigate the reasons for the low effectiveness of the retention mechanisms.
- works, but does not pay off, in such a case, you can try to achieve profitability through more selective application of retention mechanisms.
- works and pays off, in this case, you can move forward and achieve even greater profitability through smarter application of retention mechanisms.

uplift modeling involves training two ML models that will predict user churn 
- a model that predicts whether a user will leave if no interventions are applied. To train this model, data from the control group of the experiment should be used.
- a model that predicts whether a user will leave even if interventions are applied, to train this model, data from the test group of the experiment should be used:

How to apply model: 
- for each active user, we will apply both trained models and compare their predictions.
- next, we calculate the ratio of the probability that a user will leave with interventions over the probability that a user will leave without interventions.
- the smaller this value, the stronger the influence of retention mechanisms on the user's decision
- the final step is to select a threshold for including users in the motivation program, ensuring that the retention project is cost-effective by comparing the total retention costs with the benefits of retaining users.


# Telco Customer Churn Project 
The project consists of 4 main steps: 
- data preprocessing and model development (CatBoost)
- interface (streamlit)
- API (fastAPI)
- Automation (Docker)



