# Classification_Model_Optimization

# Selecting Classification Thresholds i.e. Selecting Recall/Precision/Accuracy as per industry requirements 

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


# 3.Heart Disease Diagnosis

Here our target is 1 which means 'Risk of Heart Disease' or target is 0 which means No heart Disease.

For selecting classification threshold we need to understand what TP, TN, FP, FN explains in business terms.

-TP: Person has a Risk of Heart disease and it is predicting that there is a risk of disease.

-TN: Person has a No Heart disease and it is predicting that there is no heart disease.

-FP: Person has a No Heart disease and it is predicting that there is a risk of disease.

-FN: Person has a Risk of Heart disease and it is predicting that there is no heart disease.

Here I think we should focus on Recall metrics because False Negative seems to be a costly parametere, as if we predict no heart disease for a person with a high risk of heart disease that person might die from a heart attack. We need to predict false negatives correctly because someone's life is at stake. we need lowest False Negatives possible with highest acuracy in such a manner that we can save people's life by taking precautionary actions.

So we need to select classification threshold and performance measure in such a way that we are decreasing the False Negatives i.e. we should focus on Recall

s we discussed above we need to choose the performance metrics in such a way that we are decreasing the false negatives and we can say in a way we are increasing the true positives. For doing that we need to choose the "Recall" metrics to increase.

Recall metrics would be larger if we are able to decrease the False Negatives. From above table we can see that for threshold of 0.20, FN % is 0 and Recall is max = 1.

Talking about the model performance we can say that the logistic test data is performing better than the trainig data with almost similar accuracy and higher Recall. Please refer below for the metrics.

Accuracy of the Model is : 89.01
Recall of the Model is : 96.23
Accuracy of the Model (Train) is : 84.91
Recall of the Model (Train) : 89.29
But we need to increase our recall more, as we trying to eliminate all the posibilites of false classification of a patient who might have chances of heart disease.

Our focus is to increase the Recall parameter for better business decisions. As discussed from the above table we can choose the threshold of 0.2 to increase both the model performance & the recall which is our main target.

But with default threshold of 0.5 our model is not performing bad, it seems to me as Excellent in case of both recall and accuracy but would depend purely on the Business perpective of the model, what exatly we are looking for.

Rating the effective of the above model I can say it is performing Excellently.

I woule be choosing threshold = 0.20 to achive Max Recall with high accuracy.

As I discussed above our main focus is to increase the Recall with highest accuracy, as we want our model to minimize the False Negatives. Reducing False Negatives means we are reducing the chance of not detecting a risk of heat disease when the risk actually exists. For this we applied different methods like Grid Search best estimaror & Cost comlexity pruning to find the optimal hyperparameters & alphas to build a better model.

As per above results I was able to achieve the accuracy of 85.5% with a recall of 92.7%, which means we are able to detect that 92.7% of people who has risk of heart disease are predicted correctly with an accuracy of 85.5%%, these parameters are of tested datatsets.

Comparing with the training data sets without CCP the model was getting overfitted. but with the help of pruning we were able to achieve a good model. The beaauty of this model is that we were able to achive larger vaues of Recall, please refer below the parameter metrics acieved after pruning.

**Accuracy of the model : 0.855

**Recall of the model : 0.927

**Model Train accuracy is : 0.802

**Model Train Recall is : 0.911

Over fitting and similar results for hyperparameter tuning is due to comparatively smaller data set, as while cross validation we donot have much data to play with. Similar datasets are getting chosen for cross validation. This problem was dicarded by chosing optimum value of alpha.

I choosed alpha = 0.023243 to build the model which improved both the model accuracy and recall.

Now talking about the effectiveness of our Model we can say that the model is Adequate because with higher Accuracy & Recall it is going to classify, but not Excellent because we should test it with more data. Excellent effictiveness can be achieved if we would be able to Increas recall to 100 % and Accuracy to atmost 90%-95%. Then we would decrease the possiblily of wrong classification of the risks of heart disease and save more lives.
