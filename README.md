# Predicting-Telephonic-Marketing-Outcome-for-Bank-Term-Deposit
__The Problem__

- The Problem that we intent to present is 'Predicting Telephonic Marketing Outcome for Bank Term Deposit'
- The problem link is https://archive.ics.uci.edu/ml/datasets/Bank+Marketing
- The Dataset was collected From a Portuguese Bank from May 2008 to November 2010 
- The Mode of Marketing was telephonic 
- The product that the Bank pitched to its customers was 'bank term deposit'
- We tried to predict weather a customer would subscribe the pitched product or not

__The Dataset__

- The Dataset had 20 attributes (10 numeral and 10 categorical)
- The Dataset contained missing values in the categorical data but they were encoded as 'unknown'
- We replaced the 'unknown' label with their appropriate names
- The Dataset was highly unbalanced with 11.27% positive points and 88.73% negative points

__The KPI__

- The KPI that we tracked in this case are F1-Score, AUC, Log-Loss

__The Models__

- On the Datasets we Trained The corresponding ML Models
- 1. Logistic Regression
- 2. Naive Bayes
- 3. Linear SVM
- 4. Decision Tree
- 5. Random Forest
- 6. XGBoost
- 7. Simple Neural Network
- 8. Stacking Classifier
- 9. Voting Classifier

__Feature Engineering__

- For each numeral feature we added sin(feature) to the Dataset
- For each numeral Feature we trained a 'Decision Stump' and got the weighted F1-Score of the Model
- If the F1-Score was greater than 0.85 we converted the numeral feature to categorical feature based on the 'Decision Stump' thresholds

__Different Approaches and Experimentation__

- Now from the Dataset we have the engineered sine features and the engineered Categorical Features
- From this we Experimented the Models with 4 approaches
- Approach 1. Train the Models without any Feature Engineering(Only on the 20 base Features)
- Approach 2. Train the Models on Base Features and the Sine Features(20 base Features and 10 sine Features)
- Approach 3. Train the Models on Base Features and the Engineered Categorical Features (20 base Features and 4 engineered categorical Features)
- Approach 4. Train the Models on Base Features, the Sine Features and the Engineered Categorical Features (20 base Features, 10 sine Features and 4 engineered categorical Features)

__After Experimenting with all the approaches the results are as follows__

__Features: 20 base Features__                            
- Classifier: XGBoost Classifier 
- F1-Score: 0.91257  

__Features: 20 base Features and 10 sine Features__                  
- Classifier: Voting Classifier  
- F1-Score: 0.91237  

__Features: 20 base Features and 4 engineered categorical Features__          
- Classifier: Stacking Classifier 
- F1-Score: 0.94928  

__Features:20 base Features, 10 sine Features and 4 engineered categorical Features__ 
- Classifier: Stacking Classifier
- F1-Score: 0.95697  


__Conclusions__

- From the Above Table we see that the Stacking Classifier applied on all Features performs the best with weighted F1-Score of 0.9569
- After comparing the Confusion Matrix for all the models, we can observe that The Confusion Matrix of Stacking Model applied on all the features is the Best
- Also the stacking Classifier applied on all the features has very less false negative values which is very good as the Model will not mark positive points as negative points and hence the Bank will not loose many genuine customers in the Marketing Process
- The Precession for the positives points is 0.716 for the best Model and this means that Out of the Points that the model marked as Positive points around 70% of them are genuine
- Thus we were able to classify the given Bank Marketing Dataset
