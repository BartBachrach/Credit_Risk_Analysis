# Overview
The lending company LendingClub has tasked us to create a machine learning model to predict credit risk. Lending is inherently an unbalanced game in terms of good to bad loans, as good loans will far outweigh bad loans every day of the week. Out of 100,000 bad loans, 10-20 might be bad loans, but LendingClub, like any sensible lender, wishes to reduce the risk of bad loans to its lowest possible degree. 

Our analysis involved deploying various machine learning methods to assess credit risk, with varying degrees of accuracy and precision. We used a sample dataset to train the models, and while we want to be accurate and precise, those two concepts are inherently a balancing act, and we cannot be too precise or accurate with our training set, because the model will not work well in the wild. Machine learning is kind of like designing a sneaker: the more you fit it to your test wearers, the less the shoes will work for the general population, but you also don’t want them too loose or unable to work with the majority of the population. 

# Results
The first method we used was random OVERsampling, meaning we took the minority of the dataset (the bad loans) and synthetically matched it to the size of the majority so we had an equal amount of both. The precision score for ALL methods was 99%
The precision score was 99%, while the recall score (sensitivity) was 69%, meaning that more loans were labeled as risky than actually were. In lending you would say the mortgage officer is overcautious. 
The balanced accuracy score was 65%, overall better than worse, and an acceptable score, not too well fitted, not too loose fitting either

The next method we deployed was random UNDERsampling, where we did the opposite of the previous model: we scaled down the majority (good loans) to match the size of the minority. 
* The precision score for this model was 99%, with a recall score of 45%, worse than the oversampling model. In other words, this model only predicts 45/100 true positives. In other words, this model is worse than it is good at making a prediction. 
* The balanced accuracy score was 52%; you would be about as good yourself with a flip of a coin. 
We then used a combination of the above, referred to as SMOTEENN, or Synthetic Minority Oversampling TEchnique Edited Nearest Neighbors. 
* The precision was again 99% for this model, but the recall score was 53%, .01 better than undersampling, and again, you would do about as well flipping a coin. 
* The balanced accuracy score was 62%, better than the undersampling model, but probably would need some improvement.
We then used a method called Balanced Random Forest Classifier, wherein it created multiple decision trees (hence the name) to make predictions. 
* This method returned a 99% precision score, and a recall score of 94%. While that looks great, it is perhaps too well fitted to this sample data set, and would need some adjustment before being deployed for real world application.
* The balanced accuracy score was an admirable 76%; with some adjustment this could be a winning strategy.
Last we used the AdaBoost EasyEnsembleClassifier, the first part meaning Adaptive Boost, to make predictions. 
* Its precision score was 99% and like the previous model, it had a recall score of 94%; again.
* The balanced accuracy score was 92%, meaning this model was definitely too well fitted to the model, and would most likely perform poorly in the real world. 

## Summary
The above machine learning models produced a wide range of results with some performing well, some poorly, and some too well. We discovered that machine learning can enhance the business practices of LendingClub and better inform their decisions on whether or not to extend a line of credit to a customer. With further sample data from their business we could further hone the models to best predict the outcome of a line of credit.

## Recommendation
This analyst recommends the random oversampling model, with a sensitivity of 69% the model predicts more accurately than random chance, but is also not too well fitted to the training dataset. In the wild, with additional training and enhancement, it shows the most promise for boosting the profitability of LendingClub. 
