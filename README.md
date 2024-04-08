# German-Credit-Data
The CRISP-DM data mining process – Statlog  (German Credit Data)
## Business Understanding
Banks and credit card companies rely on data mining to assess individuals' creditworthiness, reducing the risk of lending to those who may not repay. This process involves analyzing past spending and payment behaviors to make more accurate lending decisions, ensuring the business's financial strength and ability to serve more customers.

## Data Understanding
The dataset contains 1000 entries with 21 columns, featuring a mix of numerical and categorical variables. Numerical attributes like 'duration', 'amount', 'inst_rate', and others offer quantitative insights into credit profiles. Categorical variables such as 'checkin_acc', 'credit_history', and 'purpose' provide qualitative context on employment status, personal attributes, and credit history. The 'status' column, serving as the target variable, is binary, with 1 representing 'Good' creditworthiness and 2 representing 'Bad'. This column guides predictive models in forecasting credit outcomes based on other column data.

## Data Preparation
Data preparation before fitting into a machine learning model is crucial to ensure the dataset is structured, cleaned, and encoded according to the model’s input requirements. Our dataset underwent several preprocessing stages to optimize it for accurate predictive outcomes.

Initially, the target variable 'status' representing credit rating was separated from the feature set. Dummy variables were then created for categorical attributes, expanding them into binary columns for modeling purposes. For example, the 'checkin_acc' column was split into multiple binary columns to represent specific checking account categories numerically.

Next, the response variable 'status' was converted into binary labels, with 'Good' represented by 0 and 'Bad' by 1, simplifying prediction labels for the model. The dataset was partitioned into a 90-10 split for training and testing, ensuring diverse data for accurate model evaluation.

Scaling was performed to standardize the data, reshaping it to a standard scale using a StandardScaler to ensure uniform feature contribution in algorithms.

Furthermore, a RandomForestClassifier was employed to determine feature importance, aiding in understanding each attribute's contribution to the model. Based on importance scores, features were selected or omitted, with 35 features selected for model fitting based on a predefined threshold.

In conclusion, various data preparation stages, including encoding, scaling, and feature selection, optimized the dataset for effective model training and evaluation.

## Modeling
In this phase, we employed Logistic Regression and Random Forest Classifier models to tackle our credit scoring challenge. We evaluated their performance using metrics like accuracy, precision, recall, and F1-score, alongside conducting hyperparameter tuning to enhance their effectiveness.

Logistic Regression Results:
- Achieved 78% accuracy on the test data.
- Precision, recall, and F1-score for predicting bad credits (1) were 0.62, indicating balanced performance in identifying the positive class.

Random Forest Classifier Results:
- Attained 72% accuracy on the test data.
- Precision and recall for identifying bad credits (1) were comparatively lower than the logistic regression model.

Hyperparameter Tuning:
For Logistic Regression, we tuned hyperparameters such as the regularization constant (C), penalty, and solver using GridSearchCV. The best parameters were {'C': 0.1, 'penalty': 'l2', 'solver': 'liblinear'}. Applying these parameters maintained the accuracy at 78%.

Visualizations:
Confusion Matrix: Revealed correct identification of 60 good credits and 18 bad credits, with 11 false positives and 11 false negatives. This insight highlights areas for model improvement in terms of false positives and negatives.


[image](https://github.com/MounikaKoppole/German-Credit-Data/assets/113781162/16c4b971-594f-477c-9175-36e42ffe9583)


ROC Curve: Showed a stepwise increase, plateauing at an accuracy rate of 0.6, indicating a reasonable balance between true positive and false positive rates, suggesting room for enhancement.

Precision-Recall Curve: Demonstrated a balanced trade-off between precision and recall for different thresholds, essential for correctly identifying positive instances and labeling negative instances as negative in a credit scoring model where both types of errors have significant consequences.

[image](https://github.com/MounikaKoppole/German-Credit-Data/assets/113781162/f14e96bf-851b-4115-99a3-4bf5894f98c3)


## Conclusion on Modeling:
The Logistic Regression model showed better balance in identifying good and bad credits compared to Random Forest. Hyperparameter tuning refined the models, though accuracy remained constant. Visualizations like the confusion matrix and ROC curve highlighted areas for improvement in reliability and robustness for credit scoring.

## Evaluation:
While achieving a promising 78% accuracy, deeper analysis is needed:
- False Positives and Negatives: Both were observed, posing risks of bad debt and missed opportunities.
- Precision and Recall: Balanced precision and recall are crucial for identifying bad loans and potential good ones.
- Robustness: Further evaluation is required to ensure the model can handle diverse profiles and economic conditions.

The results show promise, but comprehensive evaluation, including cost-benefit analysis and customer relationship impacts, is necessary before implementing the models.

## Deployment

### Benefits:
● Automated Decision-Making: Implementing the model could automate the credit scoring process, making it more efficient.
● Risk Mitigation: The model can help in identifying potential bad loans, thus reducing the risk of bad debt.

### Concerns and Issues:
● Model Interpretability: Logistic Regression is interpretable, but ensuring that stakeholders understand and trust the model’s decisions is essential.
● Data Privacy and Ethics: Ensuring that customer data is handled securely and ethically is paramount.
● Changing Economic Environments: The model should be resilient and adaptable to varying economic climates, which needs continuous monitoring and tuning.

### Wisdom from the Project:
● Importance of Data Preparation: Significant insights were gained regarding the pivotal role of data preprocessing and feature selection in improving model performance.
● Model Evaluation: A deeper appreciation was cultivated for holistic model evaluation beyond accuracy, considering business impacts like false positives and negatives.
● Continuous Improvement: Recognizing the necessity for continuous model monitoring, evaluation, and improvement for adapting to evolving conditions and improving decision-making.

Made With ❤️ by Sai Mounika Koppolu 
