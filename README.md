# Fraud Detection Project

## Business Description
Fraud detection is a critical component in safeguarding businesses and industries against deceptive activities. As organizations increasingly rely on digital transactions and data-driven operations, the need for robust fraud detection mechanisms becomes crucial.

## What is Fraud Detection used for?

Fraud detection serves as a proactive measure to identify and mitigate instances of deceit, unauthorized access, or malicious activities within a system. The primary goal is to ensure the integrity of transactions, protect sensitive information, and maintain the trust of stakeholders.

## The Importance of Fraud Detection

The repercussions of fraud extend beyond financial losses, including damage to reputation, deterioration of customer trust, and potential legal ramifications. By implementing data science techniques, businesses can enhance their ability to detect and prevent fraudulent activities, thereby strengthening their security posture and preserving the reliability of their operations.

## Challenges of Fraud Detection

Despite its significance, fraud detection presents multifaceted challenges. The always-changing game of fraudulent tactics, the substantial volume of data to analyze, and the challenge presented by the balance between false positives and false negatives constitute ongoing challenges. This project aims to navigate these hurdles with data science approaches in order to create a robust fraud detection system.

## Project Solution 

**Problem definition:** Fraud detection. Constructing a mechanism for the financial institution using data science techniques to improve the security infrastructure and elevate the precision of decision-making processes.

**Data collection:** [Kaggle](https://www.kaggle.com/datasets/gopalmahadevan/fraud-detection-example) dataset download.

**Data cleaning and processing:** The dataset didn't have any missing values, but the name of the columns were changed to avoid confusion. 

**Exploratory Data Analysis:** This section was used to clarify some information about the dataset, like the the distribution of step (hours) on transactions, the type of payments distribution and how they were related to the amount of money. Using visual analysis we could see that the hour 9 had the most transactions and the type "transfer" was the most used. Unfortunately, the fraud data was so small that the distribution could not be clearly seen.

**Data preparation:** Some columns were dropped because they were not useful for the model, like flagged_fraud with all values equal to zero and name_orig because all values were unique. **One-Hot Encoding** was applied to the type of payment, **Label Encoder** for the transaction recipient and **Robust Scaler** for the columns in monetary values. 

**Data modeling:** By applying **Logistic Regression**, the model returned a high *Accuracy* result and small *Recall*, confirming the model's unbalanced data that was a problem during EDA. Then, the data was resampled using SMOTE (Synthetic Minority Over-sampling Technique). The next step was to model the data using the Logistic Regression again, **Decision Tree Classifier** and **Random Forest Classifier**. All the models were evaluated by the metrics: *Accuracy*, *Precision*, *Recall* and *F1 Score*, plotting the *Confusion Matrix* and the *ROC curve* in each one.

**Data interpretation:** After Resampling the data the models performed well, with good results for Recall and F1 Score. By the end of it, we could see that the Random Forest Classifier was the best model.

**Applying improvements:** The hyperparameter tuning section is to improve the chosen model. A Grid of parameters were used to find the best results for the model using **RandomizedSearchCV**.

**Definition of the best model:** The best parameters were used to run the model again and returned the following results: Accuracy: 0.9743, Precision: 0.9662, Recall: 0.9828 and F1 Score: 0.9744. The high Recall result gives confidence to follow with this model throug the next steps of the project for the financial institution, identifying a fraud when needed.
