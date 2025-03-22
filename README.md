# credit-risk-classification

This repository contains the module 20 challenge results for amy millimen-tola.  This challengge was completed with the use of class example files, and I used Chat GPT to help me understand how to interpret some of the results.

The purpose of this analysis was to use historic credit and loan data to create a predictive model to assess the creditworthiness of borrowers. First, the data file was split into training and test data using train_test_split. The a logistic regression model was created using the original data. The orignal models performance was tested by generating a confusion matrix, printing a classification report, and evaluating the accuracy.  

When evaluating this original model, it was determined that the logisitic regression model is a good predictor of healthy vs high-risk loans.  The accuracy socre of the dataset was very high at .9939 (99%). Additionally, the confusion matrix assesses a high number of true negatives (18673) and true positives(593). The results from the classification report indicate that the model predicts a healthy loan 100% of the time. For the high risk category, the 95% recall indicates the model is typicaly correct, but the 87% precision indicates some healthy loans are being predicted as high risk.  

Training Data Score: 0.993912505158894
Original Data Classification Report:  
                  precision    recall  f1-score   support
    
         Healthy       1.00      1.00      1.00     18759
       High Risk       0.87      0.95      0.91       625
    
        accuracy                           0.99     19384
       macro avg       0.94      0.97      0.95     19384
    weighted avg       0.99      0.99      0.99     19384

To attempt to improve the prediction model, the data was resampled using "RandomOverSample", then the same analysis steps were repeated with the resampled data. With the oversampled data, the logistic regression accuracy decreased slightly overall, but the models ability to predict unhealthy loans improved, while the Healthy Loan predictions became slightly less accurate. With the higher precision of hte high risk loans, there are fewer false positives in the high risk category, but the model is still predicting health loans correclty at a very high rate. 

Training Data Score: 0.9659008120546582
Resampled Data Report: 
              precision    recall  f1-score   support

     Healthy       0.94      0.99      0.97     56277
   High Risk       0.99      0.94      0.96     56277

    accuracy                           0.97    112554
   macro avg       0.97      0.97      0.97    112554
weighted avg       0.97      0.97      0.97    112554

If the intention of the model for the company is to determine which loan candidates are high risk more accurately, the sampled data model is the better predictor with a higher Recall, Precision and f1-score.  If the intention of the model is to accurately predict the healhy loan candidates, the original model is the better choice.  
