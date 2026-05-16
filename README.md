# Customer Churn Prediction using Machine Learning

---

# Project Overview

Customer churn is one of the major challenges faced by subscription-based businesses such as telecom companies, internet service providers, banks, and digital platforms. Churn occurs when customers stop using a company’s products or services.

This project focuses on analysing customer behaviour patterns and building machine learning models to predict whether a customer is likely to churn. By identifying potential churn customers in advance, businesses can take proactive retention measures and minimize revenue loss.

---

# 1. Business Problem Understanding

## What is Churn?

Churn refers to the situation where customers discontinue or stop using a company’s services.

Example:
- A telecom customer switching to another network provider
- A streaming platform subscriber cancelling the subscription

---

## Why Churn is a Business Problem?

Customer churn directly affects:

- Company revenue
- Market share
- Customer growth
- Brand reputation

Acquiring a new customer is usually much more expensive than retaining an existing customer. High churn rates indicate customer dissatisfaction and weak customer retention strategies.

---

## Why Predicting Churn is Useful?

Predicting churn helps businesses:

- Identify customers likely to leave
- Take preventive retention actions
- Improve customer satisfaction
- Reduce financial losses
- Design targeted marketing campaigns
- Increase customer lifetime value

---

## Why Customer Retention is Important?

Customer retention is important because:

- Existing customers generate recurring revenue
- Loyal customers are more profitable
- Retention reduces acquisition costs
- Satisfied customers improve brand reputation
- Long-term customers are easier to upsell and cross-sell

---

## Why False Negatives are More Costly?

In churn prediction:

### False Negative

The model predicts that a customer will stay, but the customer actually churns.

This is dangerous because:
- The company fails to identify an at-risk customer
- No retention strategy is applied
- Revenue is lost unexpectedly

### False Positive

The model predicts churn, but the customer actually stays.

This may only result in:
- Unnecessary promotional offers
- Small additional retention cost

Therefore, False Negatives are usually more expensive than False Positives.

---

# 2. Data Understanding

## Dataset Description

The dataset contains customer demographic information, service usage details, payment behaviour, and churn status.

The objective is to predict whether a customer will churn or not.

---

# Dataset Features Description

| Feature Name | Description |
|---|---|
| CustomerID | Unique identification number assigned to each customer. |
| Gender | Represents the gender of the customer. |
| SeniorCitizen | Indicates whether the customer is a senior citizen. |
| Partner | Shows whether the customer has a partner or spouse. |
| Dependents | Indicates whether the customer has dependents. |
| Tenure | Number of months the customer stayed with the company. |
| PhoneService | whether the customer uses phone service. |
| MultipleLines | whether the customer has multiple phone connections under the same account. |
| InternetService | Type of internet service subscribed by the customer. |
| OnlineSecurity | Represents whether the customer has subscribed to online security services. |
| OnlineBackup | Indicates whether the customer uses online backup services. |
| DeviceProtection | Shows whether the customer has device protection services. |
| TechSupport | Represents whether the customer has access to technical support services. |
| StreamingTV | Specifies whether the customer subscribes to TV streaming services. |
| StreamingMovies | Indicates whether the customer uses movie streaming services. |
| Contract | Indicates the contract type selected by the customer. |
| PaperlessBilling | Indicates whether the customer uses paperless billing. |
| PaymentMethod | Describes the payment method used by the customer. |
| MonthlyCharges | Monthly amount charged to the customer. |
| TotalCharges | Total amount charged during the customer relationship. |
| Churn | Target variable indicating whether the customer left the company. |

---

## Numerical Columns

The following columns are numerical:

- SeniorCitizen
- Tenure
- MonthlyCharges
- TotalCharges

---

## Categorical Columns

The following columns are categorical:

- Gender
- Partner
- Dependents
- PhoneService
- MultipleLines
- InternetService
- OnlineSecurity
- OnlineBackup
- DeviceProtection
- StreamingTV
- StreamingMovies
- TechSupport
- Contract
- PaperlessBilling
- PaymentMethod
- Churn

---

## Target Variable

### Churn

- Yes → Customer left the company
- No → Customer stayed with the company

This is the output variable that the machine learning model predicts.

---

## Problem Type

This is a:

# Classification Problem

Because the target variable contains categories:
- Churn
- Non-Churn

The objective is to classify customers into these categories.

---

## Why This is a Supervised Learning Problem?

This is supervised learning because:

- The dataset contains input features (customer information)
- The dataset also contains known output labels (`Churn`)
- The model learns patterns from labeled historical data

---

# Project Objectives

The main objectives of this project are:

- Analyse customer churn patterns
- Identify important churn factors
- Build machine learning models
- Predict customer churn
- Categorize customer risk levels
- Suggest business retention strategies

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- sklearn
---

# Data Cleaning and Preprocessing

Several preprocessing steps were performed before model building.

---

## 1. Handling Missing Values

- Checked dataset for null values
- Missing numerical values (TotalCharges) were replaced using median values

---

## 2. Correcting Data Types

- Converted `TotalCharges` column into numeric datatype

---

## 3. Removing Irrelevant Columns

- Removed `CustomerID` because it does not contribute to prediction

---

## 4. Encoding Categorical Variables

Machine learning models cannot process text data directly.

### Label Encoding

Used for binary categorical columns.

### One-Hot Encoding

Used for columns containing multiple categories.

---

## 5. Feature Scaling

Applied `StandardScaler` to normalize numerical columns for models 

---

## 6. Train-Test Split

Dataset was divided into:

- 80% Training Data
- 20% Testing Data

---

# Exploratory Data Analysis (EDA)

EDA was performed to identify churn trends and customer behaviour patterns.

---

## Overall Churn Rate

The analysis showed that a noticeable percentage of customers left the service, indicating customer retention challenges.

---

## Churn by Contract Type

Customers with month-to-month contracts had the highest churn rate compared to yearly contract customers.

### Business Insight

Long-term contracts improve customer retention.

---

## Churn by Tenure

Customers with shorter tenure were more likely to churn.

### Business Insight

New customers require stronger engagement and onboarding support.

---

## Churn by Monthly Charges

Customers with higher monthly charges showed increased churn probability.

### Business Insight

High pricing may negatively impact customer satisfaction.

---

## Churn by Payment Method

Customers using electronic check payment methods showed relatively higher churn rates.

### Business Insight

Automatic payment methods may improve retention.

---

## Churn by Internet Service

Fiber optic customers displayed higher churn behaviours.

### Business Insight

Customers paying premium charges may have higher service expectations.

---

## Churn by Senior Citizen Status

Senior citizens showed different churn patterns compared to younger customers.

### Business Insight

Specific customer segments may require personalized retention strategies.

---

# Machine Learning Models Used

The following classification models were implemented:

---

## 1. Logistic Regression

- Simple and interpretable
- Effective for binary classification problems

---

## 2. Decision Tree Classifier

- Handles non-linear relationships
- Easy to visualize and understand

---


# Model Evaluation Metrics

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

---

# Confusion Matrix

| Actual / Predicted | Predicted Churn | Predicted Non-Churn |
|---|---|---|
| Actual Churn | True Positive (TP) | False Negative (FN) |
| Actual Non-Churn | False Positive (FP) | True Negative (TN) |

---

# Business Meaning of Confusion Matrix

## True Positive (TP)

Customers correctly predicted as churn customers.

### Business Meaning

The company can target these customers using retention offers.

---

## True Negative (TN)

Customers correctly predicted as non-churn customers.

### Business Meaning

These customers are stable and loyal.

---

## False Positive (FP)

Customers predicted as churn customers but actually stayed.

### Business Meaning

The company may spend unnecessary retention costs.

---

## False Negative (FN)

Customers predicted as non-churn but actually churned.

### Business Meaning

This is the most dangerous situation because the company loses customers unexpectedly.

---

# Model Evaluation Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Logistic Regression (Churn) | 70% | 0.60 | 0.55 | 0.57 |
| Decision Tree (Churn)| 61% | 0.46 | 0.52 | 0.49 |


---

# Final Model Selection

## Selected Model: Logistic Regression

---

## Reasons for Selection

When evaluating models for churn prediction, it's crucial to consider not just overall accuracy, but also specific metrics like Precision, Recall, and F1-Score, as the cost of false positives (predicting churn when a customer won't) versus false negatives (failing to predict churn when a customer will) can be very different.

**Accuracy:** Overall correctness of the model. Useful when classes are balanced.
**Precision:** Of all customers predicted to churn, what percentage actually churned? (Minimizing false positives).
**Recall:** Of all customers who actually churned, what percentage did the model correctly identify? (Minimizing false negatives).
**F1-Score:** The harmonic mean of precision and recall. A good balance between the two.
### Which metric matters most for churn prediction?
For churn prediction, Recall is often the most critical metric. Here's why:

Cost of False Negatives: A false negative means the model predicted a customer would not churn, but they did churn. These are missed opportunities for intervention. The business loses a customer without even trying to retain them.
Intervention and Retention: Businesses want to identify as many potential churners as possible so they can proactively intervene with retention strategies (e.g., special offers, personalized support). If a customer is incorrectly predicted to churn (false positive), the cost might be a wasted retention effort or a slightly annoyed customer, but the customer is still retained. If a customer who will churn is missed (false negative), the business loses them entirely.
Therefore, we typically prioritize a model that has higher Recall for the 'Churn' class (class 1), even if it means slightly lower precision or overall accuracy, because maximizing the identification of actual churners is usually the primary goal for retention efforts.

### Model Selection Based on the comparison:

**Logistic Regression** shows higher scores across Accuracy, Precision, Recall, and F1-Score for the 'Churn' class compared to the Decision Tree model.
Specifically, Logistic Regression has a Recall of 0.55 (correctly identifies 55% of actual churners), while the Decision Tree has a Recall of 0.52. Although both are not extremely high, Logistic Regression is slightly better at identifying churners.
Given that Recall is the most important metric for churn prediction (to minimize missed opportunities for intervention), Logistic Regression is the more suitable model for this business problem.
While the Decision Tree is generally easier to interpret, its performance metrics are lower in this scenario. Therefore, the Logistic Regression model provides a better balance of predictive power for our objective of identifying potential churners.

---

# Retention Recommendations

These recommendations are strategically designed based on the insights from our Exploratory Data Analysis (EDA), the Logistic Regression model's feature coefficients, and the identified customer churn risk profiles. The goal is to proactively reduce churn and improve customer lifetime value.

### 1) Targeted Offers for High-Risk Customers:
Who: Primarily High-risk customers (short tenure, month-to-month contracts, high monthly charges, Fiber optic internet, electronic check payment).
Recommendation: Offer proactive discounts or promotional bundles to high-risk customers, especially those with high monthly charges and Fiber optic service. The discount could be tied to signing a longer-term contract.
Justification: High monthly charges and month-to-month contracts are strong positive predictors of churn. Discounts can offset perceived high costs and incentivize commitment.
### 2) Contract Upgrade Offers:
Who: Focus on High-risk and Medium-risk customers, particularly those currently on month-to-month contracts.
Recommendation: Implement attractive upgrade offers to move customers from month-to-month to one-year or two-year contracts. This could include a reduced monthly rate, free premium add-ons, or a discount on total charges for committing to a longer term.
Justification: Longer-term contracts (Contract_One year, Contract_Two year) are the strongest negative predictors of churn, indicating customer loyalty and reduced churn likelihood.
### 3) Enhanced Support and Service for Specific Customer Groups:
Who: Fiber optic internet users (especially high-risk) and new customers (shorter tenure).
Recommendation: Invest in improving the customer experience for Fiber optic users. This could involve dedicated technical support, pro-active service checks, or educational content to ensure they leverage the full value of their service. For new customers, implement an early engagement program (e.g., welcome calls, usage tips, checking satisfaction).
Justification: InternetService_Fiber optic is a strong positive predictor of churn. While a premium service, it suggests customers might have higher expectations or face specific issues. Shorter Tenure is also a strong churn indicator, so early positive experiences are crucial.
### 4. Payment Method Interventions:
Who: Customers using Electronic check as their payment method.
Recommendation: Encourage a shift from Electronic check to more stable, automatic payment methods like Credit card (automatic) or Bank transfer (automatic). This can be done through incentives (e.g., small one-time credit for switching) or by highlighting the convenience and security of automatic payments.
Justification: PaymentMethod_Electronic check is a significant positive predictor of churn. This could indicate financial instability, payment processing issues, or a less committed customer segment.
### 5. Loyalty Benefits for Long-Term Customers:
Who: Low-risk customers and those approaching significant tenure milestones.
Recommendation: Introduce or enhance loyalty programs that reward long-term customers. This could include exclusive discounts, priority support, or free service upgrades at tenure milestones. Proactively communicate these benefits.
Justification: Tenure is a strong negative predictor of churn. Recognizing and rewarding loyal customers reinforces their commitment and makes them feel valued, further reducing their churn likelihood.
### 6. Proactive Monitoring and Intervention:
Who: All customers, with a focus on those showing early warning signs.
Recommendation: Implement a system to continuously monitor customer behaviour and identify micro-trends that precede churn. For example, a sudden increase in support calls, a decrease in service usage, or recent negative feedback. Automate alerts for account managers for high-risk individuals.
Justification: This recommendation integrates the model's predictive power into daily operations, allowing for dynamic and timely interventions based on individual customer data rather than generalized segments.

---

# Project Workflow

```text
Business Understanding
        ↓
Data Collection
        ↓
Data Cleaning & preprocessing
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Model Building
        ↓
Model Evaluation
        ↓
Churn Prediction
        ↓
Business Recommendations
```

---

# How to Run the Project

## Step 1: Clone Repository

```bash
git clone [<repository-link>](https://github.com/RamneetKaur2805/Customer-Churn-Prediction)
```

---

## Step 2: Open Project Folder

```bash
cd customer-churn-prediction
```

---

## Step 3: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## Step 4: Run Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook file and run all cells sequentially.

---

# Expected Output

The project generates:

- Customer churn analysis
- Visualizations and graphs
- Machine learning prediction models
- Confusion matrix
- Model performance metrics
- Customer risk segmentation
- Business retention recommendations

---

# Conclusion

This project successfully analysed customer churn behaviour and developed machine learning models to predict customer churn.

The analysis revealed that customers with:
- Short tenure
- Month-to-month contracts
- High monthly charges

are more likely to churn.

The Logistic Regression model provided the best overall performance and can help businesses proactively identify at-risk customers and improve customer retention strategies.

---
