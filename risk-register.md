# Risk Register

| Risk | Description | Impact | Mitigation |
|---|---|---|---|
| Small dataset | The dataset contains only a small number of customers. | Model results may not generalize well. | Use a larger and more representative dataset before real-world use. |
| Data leakage | Information available only after churn could enter the model. | Model performance may appear better than it really is. | Use only information available before the prediction time. |
| False positives | A customer may be incorrectly predicted as likely to churn. | Unnecessary retention actions may be taken. | Use human review before taking action. |
| False negatives | A customer who may churn could be predicted as not churning. | Potentially important customers may be missed. | Monitor recall and improve the model with more data. |
| Bias | The dataset may not represent all customer groups. | Model performance may differ between groups. | Evaluate performance across relevant customer groups. |
| Privacy | Customer information may contain sensitive or identifying data. | Unauthorized disclosure may harm customers. | Protect customer data and avoid exposing identifiers. |
| Overfitting | The model may learn patterns specific to this small dataset. | Poor performance on new customers. | Use more data and appropriate validation. |
| Poor data quality | Incorrect or missing values can affect predictions. | Reduced model reliability. | Perform data-quality checks before training. |