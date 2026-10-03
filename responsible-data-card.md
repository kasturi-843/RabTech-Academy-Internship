# Responsible Data Card

## Dataset purpose
This dataset is used to support customer churn prediction.

The goal is to identify customers who may leave the service so that the company can provide appropriate support or retention offers.

The model must not make final decisions about customers automatically. Human review should be used before taking important actions.


## Provenance and permission
The dataset is provided as customer churn training data for ML baseline modeling.

It contains 12 customer records with information about tenure, support tickets, monthly spending, last login activity, plan type, and churn status.

The exact original data collection process and consent information are not documented in the provided dataset. Therefore, the dataset should be treated as a limited training/example dataset.


## Population and representation
The dataset represents a small set of customers.

It contains customers using Basic, Standard, and Pro plans.

Because the dataset contains only 12 records, it may not represent the complete customer population.

The small sample size can limit the reliability and generalization of a machine learning model.


## Features and target
### Features

- customer_id: Unique identifier for each customer.
- tenure_months: Number of months the customer has used the service.
- support_tickets: Number of support tickets raised by the customer.
- monthly_spend_inr: Customer's monthly spending in INR.
- last_login_days: Number of days since the customer's last login.
- plan_type: Customer's subscription plan such as Basic, Standard, or Pro.
### Target

- churned: Indicates whether the customer churned.
  - 1 = Churned
  - 0 = Not churned

customer_id should not be used as a predictive feature because it is an identifier.

Potential leakage should be checked to ensure that no feature contains information that became available only after the customer churned.

## Quality checks
The dataset should be checked for:

- Missing values
- Duplicate customer IDs
- Invalid numerical values
- Outliers
- Class balance between churned and non-churned customers
- Correct data types
- Proper separation of training and testing data

The dataset is very small, so model evaluation results may have high uncertainty.

## Risks and safeguards
### Bias risk
The small dataset may not represent all customer groups.

Mitigation: Test the model on more diverse and larger datasets before real-world use.

### Privacy risk
Customer-related information should be handled carefully.

Mitigation: Avoid exposing customer identifiers and restrict access to authorized users.

### Data leakage risk
Information related to events after churn could produce misleadingly high performance.

Mitigation: Only use information available before the prediction time.

### False-positive risk
A customer may be incorrectly predicted as likely to churn.

Mitigation: Use human review before taking retention actions.

### False-negative risk
A customer who is actually going to churn may be predicted as not churning.

Mitigation: Monitor model performance and periodically retrain using appropriate data.

## Intended evaluation
The baseline should be compared with a simple non-ML baseline such as predicting the majority class.

Model evaluation should include:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

False positives and false negatives should be examined separately.

Where sufficient data is available, performance should also be checked across relevant customer groups such as plan type.

The model should be monitored after deployment and rolled back if performance or data quality becomes unacceptable.