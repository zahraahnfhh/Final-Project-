# Final-Project-

## Background
This dataset about telephonic marketing campaigns of a Protuguese banking institution. This project to make model machine learning to predict whether the client subscribe or not. 
This dataset have some columns and the final stage, we can conclude the feature selection that we choose based on feature importance to get the best performance of the model.

## Stage 1
This stage about Exploratory Data Analysis (EDA). We get insight from this stage :

<b> Descriptive Statistics <b>
 
1. The data train consists of 17 columns and 45211 rows
2. There are no duplicate data in the dataset
3. There are no missing values/null in the dataset → No need to use drop
4. The data type for each column is correct 
5. Column `age` seems to be normally distributed because it has close mean and median values
6. The `pdays` column shows the number of days that have passed since this user was contacted in the previous campaign. A value of -1 indicates that the user was not contacted in  the previous campaign
7. The `balance` column shows the total user balance in the bank. There is a negative value here, is it possible that the balance is negative (debt?)
8. In other columns there are no oddities
9. 98% of users do not default (`default`)
10. More than 80% of users do not subscribe to term deposit (`y`) → Target imbalance. It may be necessary to undersampling or oversampling
11. More than 80% of users have no debt (`loan`)
12. The `marital` column is dominated (the proportion is more than 50%) by users with married status
  
<b> Univariate Analysis <b>
  
1. Almost all columns have outliers
2. The 'day' feature has no outliers because it shows the date of the month, so the value is 1 to 31
3. Almost all features are positively skewed
4. The `day` feature appears to have 3 peaks (trimodal distribution)Suggestion:- Log transformations for highly skewed features
5. The majority of `poutcomes` (results from previous campaigns) are unknown
6. The majority of users are contacted via the contact cell (`contact`)
7. The majority of users were contacted in May
8. Distribution of users on those who have mortgages and those who don't, quite close together (`housing`)
9. Majority of users do not default (`default`)
10. The majority of users do not have debt (`loan`)
11. The majority of users do not subscribe on term deposits (`y`)
  
<b> Bivariate Analysis <b>
  
1. pdays has a weak positive correlation with previous
2. For the target column, duration has a weak positive correlation with y
3. users who do not default (no in `default`) are more likely to subscribe to term deposits
4. users who do not have debt (no in `loan`) are more likely to subscribe to term deposits
  
 <b> Business Insight <b>
   
1. The number of campaigns 1-3 seems to be the optimal amount for users to subscribe to the term deposit. The marketing team must find the optimal campaign method so that only  1 to 3 times the user is contacted, the user will want to subscribe to the deposit
   
2. The majority of users contacted by the marketing team have an age range of 30 – 40. It seems that different persuasion techniques are needed for each age category, for example:
a) For the age range of 30-40, registering for a deposit can be useful for children's tuition fees
b) For the age range 40-50, registering for a deposit can be useful for preparing for old age retirement

3. From the Contact and Duration Boxplot, customers with short calls tend to refuse deposit offers. This means that we can guess if the early minutes (1-3 minutes early) is a very decisive/crucial time to offer deposits. You must check what has been conveyed by the sales/customer success team in the first 1-3 minutes. If you don't get attention in the first 2 minutes, the customer will refuse (churn). When we can convey information well in the first 1-3 minutes, then there is a potential for success (in the category of 5-6 minutes)

<b> Business recommendations: <b>
1. Standardize the text that we will convey to customers
2. Because our products are actually good and it means that those who have used our products have a high retention rate. Then it could be the second business recommendation, namely product testimonials from previous users 2-3 minutes early in delivering benefits and testimonials
  
 
## Stage 2

<b> Data Cleansing <b>
 
1. Dataset haven't missing value
2. Dataset haven't duplicated data
3. This dataset have some outliers, so we have 2 scenario to help us choose the best performance mode on the next stage ;
 a) No handling outliers at all
 b) Handling outliers
4. Feature Transformation : In this part, we handle column `duration` and `age`with Normalization.
5. Feature Encoding : 
a) Label Encoding : This feature for binary columns `education`, `default`, `housing`, `loan`, and `y`
b) One-Hot Encoding : This feature for non-binary columns `job`, `marital`, `contact`, `poutcome`
6. Handle Class Imbalance : We have 3 scenarion;
 - Without handling at all
 - Handling undersampling
 - Handling Oversampling
  
 <b> Feature Engineering <b>
 
 1. Feature Selection : We don't need to drop feature for this model
 2. Feature Extraction :  We don't need addition feature for this model
 3. Feature Addition : If we can other option, We need some external feature additional for improve performance the model such as income, children/dependants, location, has_complaint, complaint
