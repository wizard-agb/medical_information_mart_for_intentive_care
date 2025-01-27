
# Medical Information Mart for Intensive Care (MIMIC) Dataset Predictions

## Project Intro/Objective
The purpose of this project is to predict either a binary class of HOSPITAL_EXPIRE_FLAG or a regression of the Length of Stay. 

1/26 for Regression of Length of Stay - RMSE: 3.82924

https://www.kaggle.com/competitions/dl24-length-of-stay-prediction-nn-ensembles

8/26 for Classification of HOSPITAL_EXPIRE_FLAG 
- SVM : ROC-AUC : 0.91639

https://www.kaggle.com/competitions/dl24-probability-of-death-with-svm

- KNN : ROC-AUC : 0.90703

https://www.kaggle.com/competitions/dl24-probability-of-death-with-svm/leaderboard


## Project Description
In this project, we have two objectives:

- Predict the length of stay (in days) of a patient that is entering an ICU (Intensive Care Unit) 
- Predict the probability of death of a patient that is entering an ICU (Intensive Care Unit).

### Data Overview

The dataset comes from MIMIC project (https://mimic.physionet.org/). MIMIC-III (Medical Information Mart for Intensive Care III) is a large, freely-available database comprising deidentified health-related data associated with over forty thousand patients who stayed in critical care units of the Beth Israel Deaconess Medical Center between 2001 and 2012.

### Data Preprocessing

There is additional metadata for each ICD9 (diagnosis code) that we combine and attach to the training dataset. 
We get counts, length of stay, and clean up all of the patient data. 
Many patients are also return visitors, so we create a feature for returning patients. 
We get seasonal factors as well as engineering medical features. 
We also extract text data for the different diagnosis and summarize the key words as features. 
Finally, we impute and scale the data 

### Classification Model Overview

When classifying whether a patient will expire at the hospital we use two models. 
- Support Vector Machine
- K-Nearest Neighbors 

The SVM was most efficient showing 99% ROC-AUC on the K-folds validation and 91.639% ROC-AUC on the test set. 


### Regression Model Overview 

For the regression we tested: 
- Keras 
- Ensemble

The Keras regression was most efficient using a 3 layer NN with dropout and batch_normalization. We acheived a RMSE of 3.82924. 

The Ensemble method used an ExtraTrees meta learner, with KNN, Random Forest XGBoost, Support Vector and Linear regressors in the regression task. It performed well with 4.35 RMSE on the test set. 





## Getting Started

1. Clone this repo (for help see this [tutorial](https://help.github.com/articles/cloning-a-repository/)).
    
