# Datasheet Template

As far as you can, complete the model datasheet. If you have got the data from the internet, you may not have all the information you need, but make sure you include all the information you do have. 

## Motivation

For what purpose was the dataset created?
The dataset was created for a Kaggle competition hosted by Home Credit Group to develop machine learning models that can predict the probability of a customer defaulting on a loan. The goal is to increase access to financial services by improving credit risk scoring.

Who created the dataset?
The dataset was created and published by Home Credit Group N.V., a global consumer finance provider.

Who funded the creation of the dataset?
It was funded and provided by Home Credit Group, likely as part of their open innovation and research outreach efforts.

 
## Composition

What do the instances that comprise the dataset represent?
The instances represent individual loan applicants. Each record corresponds to a unique loan application and contains information about the applicant's demographics, financial behavior, and credit history.

How many instances of each type are there?
The main dataset (application_train.csv) contains approximately 307,511 labeled instances and 122 features. The test set (application_test.csv) includes 48,744 instances without labels. Additional datasets (bureau, previous applications, credit card balances, etc.) contain millions of auxiliary records linked by customer ID.

Is there any missing data?
Yes, several features have missing values. For example, OWN_CAR_AGE, AMT_REQ_CREDIT_BUREAU_YEAR, and EXT_SOURCE_1 are among those with missing rates >10%.

Does the dataset contain data that might be considered confidential?
No personally identifiable information (PII) is included. The dataset has been anonymized. However, it includes sensitive financial and demographic information that could lead to biased outcomes if mishandled.

## Collection process

How was the data acquired?
It was internally collected by Home Credit from their real customers during loan applications and subsequent credit history updates.

If the data is a sample of a larger subset, what was the sampling strategy?
The dataset includes a broad, anonymized sample of past applicants to cover a wide range of credit profiles. Specific sampling strategy is not detailed but assumed to be representative for training models.

Over what time frame was the data collected?
The dataset likely spans multiple years of customer applications but exact time frames are not publicly specified in the Kaggle dataset description.

## Preprocessing/cleaning/labelling

Was any preprocessing/cleaning/labeling of the data done?
Yes:

Features with many missing values were dropped or imputed (e.g., mean/mode/median imputation).

Categorical variables were one-hot encoded.

New features were created by aggregating statistics from related tables (e.g., bureau, previous applications).

Outliers and anomalies were removed or capped.

Feature engineering was applied: domain-specific ratios, flags, and statistical aggregations.

Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data?
Yes, all preprocessing was performed on top of the raw Kaggle dataset files, which remain unaltered and are available in the competition dataset.
 
## Uses

What other tasks could the dataset be used for?

Credit scoring

Financial behavior analysis

Risk profiling

Customer segmentation in financial services

Risks or harms of use?

Potential bias in data reflecting historical discrimination or systemic inequality.

Over-reliance on correlated features might cause unfair exclusion of applicants.

Sensitive attributes such as age or gender (even if anonymized) might act as proxies for discrimination.

Mitigations?

Fairness audits (e.g., disparate impact analysis)

Model explainability tools like SHAP

Removal or neutralization of bias-inducing features

Are there tasks for which the dataset should not be used?

Identifying individual customers (contains no PII)

Health-related or employment-related predictions not related to creditworthiness
## Distribution

How has the dataset already been distributed?
It was distributed via Kaggle as part of the Home Credit Default Risk Competition.

Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?
Yes, it is subject to Kaggle’s terms of use and Home Credit’s competition-specific licensing. Usage is restricted to non-commercial, educational, or research purposes unless otherwise permitted.

## Maintenance

Who maintains the dataset?
The dataset is maintained and hosted by Kaggle and Home Credit. However, no long-term updates or maintenance are officially promised.

