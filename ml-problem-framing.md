# ML Problem-Framing Memo

## Problem

The goal is to predict whether a customer is likely to churn.

## Prediction Target

The target variable is `churned`.

- 1 = Customer churned
- 0 = Customer did not churn

## Unit of Observation

One row represents one customer.

## Features

The model uses:

- tenure_months
- support_tickets
- monthly_spend_inr
- last_login_days
- plan_type

`customer_id` is not used as a feature because it is only an identifier.

## Intended Action

Customers predicted as likely to churn can be identified for appropriate customer support or retention activities.

The model should support human decision-making rather than automatically making important decisions about customers.

## Non-ML Baseline

A simple baseline is to predict the majority class for every customer.

This provides a reference point for evaluating the machine-learning model.

## Evaluation Metrics

The model will be evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

## Limitations

The dataset contains only a small number of customers, so the results may not generalize to a larger customer population.