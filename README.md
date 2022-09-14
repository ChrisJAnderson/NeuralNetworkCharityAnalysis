# NeuralNetworkCharityAnalysis
## Overview of the Analysis
The purpose of this analysis is to develop and optimize a neural network to predict the probability of being approved for government funding based on a variety of factors including application type, loan amount, income amount, organization classification and type, use case, and the presence of special considerations. 
## Results
### Data Preprocessing
-I considered the column is_successful as my target variable
-I considered the following columns as features for my model: Application_Type, Affiliation, Classification, Use_Case, Organization, Status, Income_Amt, Special Considerations, and Ask_Amt
-The variables EIN and Name are not useful to the model, and have not been considered as targets or features
### Compiling, Training, and Evaluating the Model
-My final attempt at optimization included three hidden layers with 30, 20, and 20 neurons respectively. I used a relu activation function in the first layer, a relu activation function in the second layer, a sigmoid activation in the third layer, and a sigmoid activation function in the output layer.
-I was not able to achieve the target model performance after 3 attempts, although I did improve the model accuracy from ~50 percent to 66 percent.
-My initial attempt at improving accuracy was to add a third hidden layer following the rule of thumb of 2/3 the number of neurons of the last hidden layer. My second attempt built on this by increasing the number of nodes in each layer, starting with 3/4*len(X_Train[0]) then following the 2/3 rule. My third attempt at improving efficiency kept the three hidden layers, but reverted the amount of nodes in layers 1 and 2 to following the 2/3 rule, while modifying layer 3 to have as many nodes as layer 2 because I found it brought a small increase in accuracy. In this attempt I also tried to address the noisy column "ASK_AMT" by bucketing the more than 8000 values into 7 bins. 
## Summary
The optimized neural network included an additional hidden layer, more nodes, and additional preprocessing to address noisy data. It did not achieve the requested level of accuracy, 75%. I believe that with better bucketing of ASK_AMT I could have achieved higher accuracy- while I did initially try to apply some statistical rules to establish bin sizes in the end I chose arbitrary sizes of 1000. I also believe that some columns may be included in the dataframe that are not necessary, such as organization, but I decided I didn't understand the data well enough to draw that conclusion.
I would also like to try this dataset within an SVM, since there's a relatively small number of critical features here and we are essentially trying to answer a yes or no question.