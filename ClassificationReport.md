# Classification Report
A classification report is a performance evaluation tool in machine learning that is used to assess the quality of predictions made by a classification model. It provides a comprehensive overview of how well the model is performing in terms of various metrics for each class in the classification task. Key components of a classification report typically include:

1. **Precision**: Precision is the ratio of correctly predicted positive observations to the total predicted positives. It is also called Positive Predictive Value. It is a measure of a classifier's exactness. Low precision indicates a high number of false positives.
   - **Example**: Out of 100 emails your model predicted as spam, if 90 are actually spam, then the precision is 90%.
   - **Formula**: Precision = TP / (TP + FP)

2. **Recall (Sensitivity)**: Recall is the ratio of correctly predicted positive observations to the all observations in actual class. It is also called Sensitivity, Hit Rate, or True Positive Rate. It is a measure of a classifier's completeness. Low recall indicates a high number of false negatives.
   - **Example**: If there are 100 spam emails in the dataset and your model correctly identifies 80 of them as spam, then the recall is 80%.
   - **Formula**: Recall = TP / (TP + FN)

3. **F1-Score**: The F1 Score is the weighted average of Precision and Recall. Therefore, this score takes both false positives and false negatives into account. It is suitable for uneven class distribution problems.
   - **Example**: If your precision is 90% and recall is 80%, the F1-Score is 2*(0.9*0.8)/(0.9+0.8) = 0.85 or 85%.
   - **Formula**: F1-Score = 2 * (Precision * Recall) / (Precision + Recall)

4. **Support**: Support is the number of actual occurrences of the class in the specified dataset. Imbalanced support in the training data may indicate structural weaknesses in the reported scores of the classifier and could indicate the need for stratified sampling or rebalancing.
   - **Example**: If there are 200 emails in the dataset, with 100 spam and 100 not spam, then the support for each class is 100.

5. **Accuracy**:Accuracy is the ratio of correctly predicted observations to the total observations. It gives a general idea of how often the classifier is correct across all classes.
   - **Example**: If a model correctly predicts the class of 950 out of 1000 instances, the accuracy is 95%.
   - **Formula**: Accuracy = (TP + TN) / (TP + TN + FP + FN), where TP is true positives, TN is true negatives, FP is false positives, and FN is false negatives.

6. **Macro Average**: The macro average computes the metric independently for each class and then takes the average. This averaging treats all classes equally, regardless of their support (i.e., how many instances belong to each class).
   - **Example**: If you calculate the precision for each class in a multi-class classifier and then average these precision scores, you get the macro average precision.
   - **Application**: Useful when you want to understand the performance of the model on each class but don’t want class imbalance to play a role.

7. **Weighted Average**:The weighted average calculates metrics for each class, similar to the macro average, but it weights the metric of each class by its support (the number of true instances for each class). This prevents classes with fewer instances from having an equal impact on the overall metric as larger classes.
   - **Example**: In a dataset where 90% of instances belong to Class A and 10% to Class B, the weighted average will give more importance to the performance on Class A.
   - **Application**: Useful in situations where class imbalance is a concern and you want the metric to reflect the importance of each class based on its prevalence in the dataset.

**In summary**:
- **Precision** focuses on the accuracy of positive predictions.
- **Recall** focuses on the model's ability to identify all relevant instances.
- **F1-Score** balances precision and recall.
- **Support** indicates the number of actual occurrences of each class.
- **Accuracy** reflects the overall correctness of the model, indicating the proportion of true results (both true positives and true negatives) among the total number of cases examined.
- **Macro Average** treats all classes equally, calculating the metric independently for each class and then taking the average, thereby emphasizing the performance on each class equally without considering their frequency in the dataset.
- **Weighted Average** also calculates metrics for each class individually but weights the contribution of each class to the average by its prevalence, making it more relevant for imbalanced datasets where some classes are more common than others.
