# **Challenge: Predict users with a high chance of leaving a streaming platform**

A classification model will be used to map which user profile is most likely to leave your streaming platform. Understanding who the profile is that is increasing your business's churn rate is essential for taking action to reduce these losses, whether by changing sales criteria or modifying the product. 

**Disclaimer:** This project was a challenge carried out at the DNC School as a prerequisite for completing the Data Science Degree. 

## **Context**

Behind the scenes at a streaming platform, the management is concerned about the high rate of users canceling their subscriptions. The directors believe that it is possible to predict whether a user is more likely to leave the platform before this happens, and on the basis of this information take action to reduce churn.  The data scientist's goal here is to create a classification model capable of predicting whether a user is more likely to cancel their subscription on the platform or not. To do this, the company provided a csv database containing data on customer accounts.
The data provided contains information on customer accounts on the streaming platform, divided into Basic, Standard and Premium accounts, each of which offers a wider range of services than the previous one.

## **Variables**

### **Numeric variables**

**User_id:** Customer identification code
**Age:** Customer's age
**Time_on_platform:** Time the user spends on the platform on average
**Devices_connected:** Number of devices connected to the account
**Num_streaming_services:** Number of streaming services the customer has
**Num_active_profiles:** Number of active profiles on the platform.
**Avg_rating:** Average rating of the platform's content

### **Categorical variables**

**gender:** Gender of the customer (Male/Female)
**subscription_type:** Type of account (Basic/Standard/Premium)

### **Target variable**

**churned:** Whether the customer canceled the account or not (type: Int)

## **Development**

The CRISP-DM methodology was used as the basis for this case, going through the stages of Business Understanding, Data Understanding, Data Preparation and Modelling.
Initially, an analysis of the available data was carried out, using grouping, descriptive/statistical analysis and also graphics, with a view to better approaching the problem and identifying possible problems in the data. In the data preparation stage, nulls, duplicate values, outliers and type changes were dealt with, where applicable.
Next, the explanatory variables were classified into numerical and categorical variables, the latter having been converted using the Pandas get_dummies and LabelEncoder functions. The explanatory variables were then normalized to prepare them for the modelling to be carried out. The data set was then divided into a training set and a test set, and in each set, the indices were reset in order to prevent the appearance of 'NaN' values.
For the modeling, 2 different classification techniques were chosen: Logistic Regression and Random Forest Classifier. Both techniques were analyzed using their confusion matrices, as well as the following metrics: Accuracy, Balanced Accuracy F1 Score, Recall Score and ROC AUC Score. Finally, an adjustment of hyperparameters was sought using the GridSearch function, with a view to obtaining better results.

## **Conclusion**

With the optimization of the parameters, there was a worsening in Accuracy, both for training and testing. The Balanced Accuracy and ROC AUC metrics showed a very slight improvement. On the other hand, there was a significant improvement in the Precision, F1 and Recall test metrics. However, the most significant improvement was in overfitting, which was eliminated once we eliminated the training metrics close to 1, combined with the improvement in the Precision, F1 and Recall metrics. Thus, the Random Forest Classifier technique with optimized hyperparameters is preferred over Logistic Regression for predicting churn among customers.
