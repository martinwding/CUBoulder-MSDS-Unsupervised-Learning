# Customer Segmentation for a Vehicle Insurance Company
## —— Identifying and predicting customer profiles using supervised and unsupervised machine learning

<br />
<br />

## Executive Summary


<br />

-----------------------------------------------------------------------------
<br />

## Table of Contents
### Part I: Background Information (README file)
#### 1. The Business Problem
#### 2. The Goal
#### 3. The Evaluation Metrics
#### 4. Definition of Success
#### 5. Data Description
#### 6. Libraries and Version

### Part II: Data Exploration, Modelling and Evaluation (ipynb file)
#### 1. Setting up the Work Environment
#### 2. Importing the Data Set
#### 3. Exploratory Data Analysis (EDA)
#### 4. Data Cleaning and Preparation
#### 5. Segmenting Customer Profile using Clustering
#### 6. Building a Classification Model to Predict Customer Profiles
#### 7. Discussion: What was the Value of Clustering?
#### 8. Final Classification Model and Business Evaluation on Test Data
#### 9. Limitations
#### 10. Conclusion



<br />

-----------------------------------------------------------------------------
<br />

### Part I: Background Information
### 1. The Business Problem
**This project builds a customer segmentation model for predicting customer profile categories** using data from a hypothetical motor insurance company. The insurance company currently charges an identical policy premium to all customers. However, not all customers are alike; by understanding customer segments and profiles, the vehicle insurance company will be able to offer more tailored premiums and services to their customers. This will help the company improve customer satisfaction and profitability.


**How are customers different?** 

Customers can be different on many dimensions. The most important dimension from an insurance company's perspective is the customer's risk profile. The riskier the customer, the more are likely that they will make higher claims and bring more costs to the company. The high-risk customers should be identified by the insurer and be charged a higher premium accordinly.


**How can insurance companies identify customer profiles?** 
Insurance companies can identify customer and risk profiles through analyzing customer characteristics. Traditionally, domain knowledge experts will look at the customer data row-by-row and design rules to categorize customers into different risk segments. In this project we will employ modern unsupervised machine learning methods to automatically categorize customers into segments based on existing data, and we will then train a supervised machine learning model for predicting customer segments on new data. The insurance company can use our model to predict whether a new customer is likely to be a high-risk or low-risk customer, and offer them an appropriate premium. 


<br />

-----------------------------------------------------------------------------
<br />


### 2. The Goal
Our goal is to build a clustering model that effectively segments customers into different customer profiles. Based on the clustering labels, we will then build a classification model that accurately predicts customer risk profiles, so that the insurance company can assign an appropriate policy premium when they sign up new customers. 


<br />

-----------------------------------------------------------------------------
<br />


### 3. The Evaluation Metrics 
Common evaluation metrics for classfication models include: accuracy, precision, recall, F1-score, and lift/gain charts. While for clustering, popular metrics include silhouette coefficient and Rand scores. There is no single metric that fits all problems.

The best metric to use will depend on the data and on the business problem that we are trying to solve. For our project, we will use accuracy for the classification model if cluster label distributions come out balanced, and we will use the F1-score if there exists large class imbalance in the cluster labels. For the clustering models, we will rely more on business intuitions rather than any particular statistical metric. Our goal is to identify customer segmentations that allow us to understand customer and risk profiles, therefore the models that provide clearer separation of customer groups in terms claims costs (a measure for risk) will be considered better models.


<br />

-----------------------------------------------------------------------------
<br />


### 4. Definition of Success
The insurer's current benchmark is charging $716.53 premium to all customers. This practice is clearly suboptimal.

To be considered successful, our model should be able to identify at least 2 segments, one significantly below 716 dollars, while the other significantly above 716 dollars. With at least two segments like this, the insurer will be able to offer lower premiums to the low-risk customers, keeping the customers happy while still making a profit. The insurer will charge higher premiums to the high-risk group and will no longer be making a loss on them. Overall, the insurer will see an improvement in profitability.


<br />

-----------------------------------------------------------------------------
<br />

### 5. Data Description

**Data Sources**

Uploaded by: 
lakshman raj

Downloaded from:
https://www.kaggle.com/lakshmanraj/vehicle-insurance-policy

**Data Set Description**

Number of Observations: 60.4K

Number of Variables: 14 variables.

**Variable Description**

Input Variables:

1 - pol_number, policy number for the insurance policy

2 - poleffdt, auto insurance policy effective date

3 - gender, gender of driver: F, M

4 - agecat, driver's age category: 1 (youngest), 2, 3, 4, 5, 6

5 - dateofbirth, driver's date of birth

6 - credit_score, driver’s credit score(integer): 1-100, 1=poor, 100=excellent

7 - area, driver's area of residence: A, B, C, D, E, F

8 - traffic_index, traffic index of driver’s area of residence(integer): 100=country average, >100 means worse traffic conditions than average

9 - veh_age, age of vehicle(categorical): 1 (youngest), 2, 3, 4

10 - veh_body, vehicle body, coded as:
- BUS
- CONVT = convertible
- COUPE
- HBACK = hatchback
- HDTOP = hardtop
- MCARA = motorized caravan
- MIBUS = minibus
- PANVN = panel van
- RDSTR = roadster
- STNWG = station wagon
- TRUCK
- UTE = utility

11 - veh_value, vehicle value, in $10,000s

12 - claim_office, office location of claim handling agent: A, B, C, D

13 - numclaims, number of claims(integer): 0 if no claim

14 - claimcst0, claim amount: 0 if no claim

15 - annual_premium, total charged premium i.e. the cost of insurance


<br />

-----------------------------------------------------------------------------
<br />

### 6. Libraries and Version
- Numpy:       1.19.5
- Matplotlib:  3.5.1
- Pandas:      1.4.0
- Pycaret:     2.3.6
- Seaborn:     0.11.2
- Scipy:       1.8.0
- Sklearn:     0.23.2
