### insurance-customer-risk-analysis-documentation
This project was submitted in one of my classes during graduate studies. The goal was to assist the management of a fictitious insurance company, “The General,” in leveraging data available for each policyholder to gain insights into customer behavior and improve risk assessment strategies. The analysis aimed to:
- Understand the types of customers served by "The General."
- Assess customer risk levels and identify consistently high-risk customers.
- Build predictive models to estimate the quoted premium amount and better evaluate risk factors.

### Dataset
The analysis utilized four datasets:
•	Abilitech Dataset: 96,501 rows, 243 columns (customer interactions and advertising campaign impacts)
•	MasterQuote Dataset: 34,975 rows, 21 columns (insurance quotes and coverage details)
•	TheGeneral Dataset: 36,368 rows, 13 columns (policy and claim information)
•	ClaimsMaster Dataset: 10,736 rows, 16 columns

### Analysis Implemented
#### 1. Hierarchical Clustering
Hierarchical clustering was applied to segment policyholders into groups based on shared attributes.

**Methodology:**
- A subset of 1,000 observations was used due to the dataset’s size.
- Clustering was performed to create 5 distinct customer groups.

**Key Insights**

Key Insights by Group:
**Group 1:**
- Higher quoted payments
- Older, wealthier customers
- More drivers per policy
- Responsive to advertising and technology

**Group 2:**
- Youngest insured policyholders
- Lowest quoted payments
- Highly influenced by advertising
- Frequent dining out
- Potential higher health-related risks

**Group 3:**
- Moderate payment values
- Frequent dining out
- Potential higher health-related risks
- Responsive to marketing

**Group 4:**
- Moderate payment values
- Less influenced by advertising
- Less dining out
- More sedentary lifestyle
- Potentially lower risk for health and accident claims

**Group 5:**
- Higher quoted payments
- Less influenced by advertising
- Less dining out
- More sedentary lifestyle
- Potentially lower risk for health and accident claims

**Overall Recommendations:**
- Personalized marketing for Groups 1 and 2
- Price-sensitive approaches for Groups 4 and 5
- Health risk assessment for Groups 2 and 3
- Target these higher-premium Group 1 and 5 customers with loyalty programs or exclusive offers

  #### 2. Ridge Regression
Ridge regression was used to predict the quoted premium amount (MQuotedTotalPayment).

**Methodology:**
- Data was split into 70% training and 30% testing sets.
- Ridge regression was applied with an alpha value of 50.

**Results:**
R-squared: 53.9%

**Key Predictors:**
covType_Full Coverage: Significantly increased premiums.
PolicyTerm and NamedInsuredDriverPoints: Important predictors.

**Conclusion:**
Ridge regression provided robust predictions with minimal feature shrinkage. It highlighted the importance of policy coverage and term length in determining premiums.

#### 3. Decision Tree
A decision tree classifier was implemented to predict high-risk customers (those likely to file large claims).

**Methodology:**
- Dataset split: 70% training and 30% testing.
- A predefined max_depth of 5 was used.

**Performance Metrics:**
Accuracy: 85%
Precision: 71%
Recall: 65%
F1-Score: 68%

**Key Insights:**
True Positives: 355 policyholders correctly identified as high-risk (large claims).
False Positives: 142 policyholders were flagged as high-risk but were not.
False Negatives: 187 high-risk policyholders were missed by the model.
True Negatives: 1446 policyholders correctly identified as not high-risk (no large claims)

### Tools and Technologies
#### Python Libraries:
**pandas, numpy:** Data manipulation and preprocessing.
**sklearn:** Machine learning models and clustering algorithms.
**matplotlib, seaborn:** Data visualization.

### Recommendations for The General Insurance
1.	Develop targeted marketing strategies for different customer groups
2.	Create personalized insurance products based on group characteristics
3.	Use the decision tree model for initial risk assessment
4.	Consider lifestyle factors beyond traditional risk metrics
