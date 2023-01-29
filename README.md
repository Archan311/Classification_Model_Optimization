# Classification_Model_Optimization

# Selecting Classification Thresholds i.e. Selecting Recall/Precision/Accuracy for industry requiremnets 

# 1. System Administrators - Training Levels model

a. Used Sequestial Feature selector from mlxtend.feature_selection for forward and backward selection 

b. Fitted the model using logistic regression, Decison Tree 

c. Chosed particular performace metrics as per th eindustry requiremnt 

d. Optimizing the model using the probility thresholds 
In this case we have to decrease the False Positives which means we need to increase True Positives i.e. increasing "Presicion"  along with Maximum "accuracy".

e. One Hot ENcoding also used to convert categorial values to numerical values

f. Used grid search CV after tuning the parameters for DT

g. We can see if the model overfitting or notby comparing  results of performce meterics of train and test sets

h. Now used cost complexity to improve the recall scores and avoiding the overfitting

i. determinig the dest alpha

j. Achieved Accuracy of 89.5 % and Precision of 100 % 

# 2. Boston Housing - House Price model 

Here we are focusing on Recall 
Achieved accuracy of 96.9% and Recall of 98.2 % using similar steps mentioned above.

CAT.MEDV Is median value of owner-occupied homes in tract above 30,000

For selecting classification threshold we need to understand what TP, TN, FP, FN explains in business terms.

-TP: Median value of owner-occupied homes is above 30,000 and it is predicting that the cost is above 30,000

-TN: Median value of owner-occupied homes is not above 30,000 and it is predicting that the cost is not above 30,000

-FP: Median value of owner-occupied homes is not above 30,000 and it is predicting that the cost is above 30,000

-FN: Median value of owner-occupied homes is above 30,000 and it is predicting that the cost is not above 30,000

Considering we are sellers,for us FN is very costly parameter because it is predicting that the Median value of owner-occupied homes is above $30,000 and it is predicting that the cost is not above 30,000. Here if we look from the business perspective it is not good because we would end up selling costly house in less price and we woule be in loss. To minimize the loss we should focus on decreasing the False Negative which means we should focus on Recall.

So we need to select classification threshold and performance measure in such a way that we are decreasing the False Negatives i.e. we should focus on Recall

As we have to choose performance metrics in such a way that we are getting highest Recall with highest Accuracy, calculating all the values of recall for different values of thresholds.

From above table we can see that for the threshold value of 0.4 we are getting highest recall of 0.96 with an accuracy of 0.95 or say 95% which is good number. It means with 95 % accuracy we would be able to predict correctly if the cost of the house is above 30,000 or not.

Talking about the model performance we can say that the logistic test data is giving a better performance than the train data set. Recall of the model is 91.3% with an accuracy of 95.39 which is better than the training dataset.

Accuracy of the Test Model is : 95.39
Recall of the Test Model is : 91.3
Accuracy of the Train Model is : 94.63
Recall of the Train Model is : 78.69
Our focus is to increase the Recall parameter for better business decisions. As discussed from the above table we can choose the threshold of 0.4 to increase both the model performance & the recall which is our main target.

As I discussed above our main focus is to increase the Recall with highest accuracy, as we want our model to minimize the False Negatives. Reducing False Negatives means we are reducing the chance of Predicting the Task Completed when it is not done. For this we applied different methods like Grid Search best estimaror & Cost comlexity pruning to find the optimal hyperparameters & alphas to build a better model.

As per above results I was able to achieve the accuracy of 96.9 % with a **Recall of 98.2%, which means we are able to predict that 75% of houses are actually Low_price with an accuracy of 96.9%, these parameters are for tested datatsets.

Now comparing with the training data sets, we ar getting pretty similar performance metrics for both training & testing data. Accuracy for training data sets is ~ 97% with recall of ~ 99%.

For this model we were able to achieve excellent performance due to optimun value of alpha which was achived due to CCP. In this case best alpha = 0.00882, is considered to achived better recall with better accuracy.
