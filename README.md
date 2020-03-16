# DIABETES ANALYSIS PROJECT

## EXECUTIVE SUMMARY 


**PROBLEM STATEMENT**

 According to the CDC’s (Centers for Disease Control) National Diabetes Statistics Report for 2020 cases of diabetes have risen to an estimated 34.2 million. In other words 10.5% of the U.S. population, have diabetes. An estimated 26.8 million people - or 10.2% of the population - had diagnosed diabetes. Approximately 7.3 million people have diabetes but have not yet been diagnosed (2018).
According to Ostling et al, patients with diabetes have almost double the chance of being hospitalized than the general population (The relationship between diabetes mellitus and 30-day readmission rates, Clinical Diabetes and Endocrinology volume 3, Article number: 3 (2017) Ostling et al). 
My project will focus on predicting hospital readmission for patients with diabetes. I will use predictive modeling(different types of machine learning methods) from data science to help identify these readmission.


**OUR OBJECTIVES**

- Search up the clinical data related to diabetes.
- Study the datasets and identify the readmission cases
    - Deploy Natural Language Processing and Bag of Word methods to convert words to words vectors
    - Explore data analysis on data
- Construct several classification models and evaluate for accuracy of predictions
- Analyze the feature importance and find useful imformation 

**EXECUTIVE SUMMARY**

*Step 1: Collect the data related to diabetes*

The database was clinical data which contain different types of valuable data from over 130 US hospitals. There are two types of data are used in my project. One is discharge summaries(NLP) that the doctor gave when the patient was discharged. Another kind is the clinical records(numerical_categorical) including patient demographics(age, sex and race) and in-hospital precedures and medications. 

*Step 2: Identify the readmission cases*

The data was extracted from the original database that satisfied the following criteria:
(1) The primary diagnose is diabete(any type).
(2) The length of stay was at least 1 day and at most 14 days.
(3) Laboratory tests were performed during the encounter.
(4) Medications were administered during the encouter.
(5) The cases of deseased are not included
(6) For readmitted for several times for each identity patient, only the first and second admission were considered.

*Step 3: Data Split and Working of Models*

Once the dataset was created and cleaned, first thing is to explore the dataset that I got. One essential fact about these two datasets is that they are both pretty unbalanced which is typical in healthcare field. The readmitted within 30 days is labeled as 1 and not readmitted or readmitted over 30 days were labeled as 0. The positvie ratio is less than 10% in both datasets. 
Several classification machine learining models were used to predict the readmission. Logistic Regression, Random Forest, XG Boost and Feed Forward Neural Network were performed badly on the unbalanced dataset. So I decided to balance the splitted training set and testing set seperately. Better performances were obtained.

The Logistic Regression couldn't converge after I tried to tuning the parameters. Other models shows different prediction abilities. I will choose the highest performing model and apply to prediction. The feature importance is explained based on this model.

In addition, the Covolutional Neural Network will be tried to work on NLP.


#### RESULTS AND DISCUSSION

*1. DATASET BALANCE*

In comparison, both datasets without balancing couldn't get a good performance for all models that I used. After training the datasets, the models couldn't correctly predict any positive. This is due to limit number of cases in the positive class. The SMOTE method was introduced to randomly sample the positive class and eventrally built a balanced dataset for train and test seperately. The unbalanced dataset in healthcare field is typical. So how to improve the performance of models on extremly unbalanced data is still need more work or update of the new models.

*2. MODEL PERFORMANCE*

Based on the performance of all models, XG Boost shows the outstanding prediction ability. It gave about 96% accuracy on NLP dataset and 94% accuracy on numerical_categorical dataset. The probabilities of predicting variables were plotted. Also the ROC curves of Multinomial NaiveBayes, Random Forest and XG Boost were plotted. The conclusion from the figures are confirmed that metrics result. We conclused that XG Boost has the most efficient predicting ability on both dataset.

*3. RESULTS OF FEATURE IMPORTANCE*

Since XG Boost shows the best results, the features from this model is studied. The feature importance were studied for both datasets. SHAP (SHapley Additive exPlanations) a unified approach to explain the output of machine learning model was used to  explain the feature importance by calculated SHAP values. Many useful predicting facts were explored. 

*4. MODEL STUDY ON NEURAL NETWORK

Neural network model was used for both dataset. It shows better performance on NLP data when I used CountVectorizer to preprocess the text file. For numerical and categorical data, neural network didn't show any advantages. More work was done with NLP data. With adding a embedding layer and hidden layer in NLP data. The model performance improved a lot. The effect of max length on accuracy was also studied. 

#### CONCLUSIONS

1.Due to the less information from the minority class, machine learning models couldn’t predict the minority class efficiently. By using SMOTE to balance the dataset can solve this problem in my study.
2.XG Boost showed much better results than other models.
3.The features in UCI data and MIMIC data were studied with SHAP values. Many useful informations were obtained from analyzing the value of each features.
4.Neural Network didn’t show success in UCI dataset. But neural network did show some significant improvement in NLP data(MIMIC dataset) when I induced the embedding matrix. 


#### CONTENTS

- CODE NOTEBOOKS
- DATA FILES
- PRESENTATION
- IMAGES
- README
   
#### SOURCE DOCUMENTATION


*Source: "MIMIC-CXR Database"*    
https://physionet.org/content/mimic-cxr/2.0.0/#files

*Source: "Diabetes 130 US hospitals for years 1999-2008"*    
https://archive.ics.uci.edu/ml/datasets/Diabetes+130-US+hospitals+for+years+1999-2008




```python

```
