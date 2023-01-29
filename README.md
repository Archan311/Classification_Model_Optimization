# Classification_Model_Optimization

I have created classification models to test three data sets

1. System Administrators - Training Levels model

a. Used Sequestial Feature selector from mlxtend.feature_selection for forward and backward selection 
b.  Fitted the model using logistic regression, Decison Tree 
c. Chosed particular performace metrics as per th eindustry requiremnt 
d. Optimizing the model using the probility thresholds 
In this case we have to decrease the False Positives which means we need to increase True Positives i.e. increasing "Presicion"  along with Maximum "accuracy".
e. One Hot ENcoding also used to convert categorial values to numerical values
f. Used grid search CV after tuning the parameters for DT
g. We can see if the model overfitting or notby comparing  results of performce meterics of train and test sets
h. Now used cost complexity to improve the recall scores and avoiding the overfitting
i. determinig the dest alpha
j. Achieved Accuracy of 89.5 % and Precision of 100 % 

2. Boston Housing - House Price model 

Here we are focusing on Recall 
Achieved accuracy o f 96.9% and Recall of 98.2 % using similar steps mentioned above

![House Pricing ](/C:/Users/anagbhid/Downloads/House_price.jpg)


