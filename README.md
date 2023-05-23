# Diabetes Prediction
#### **Data Visualization and Model Evaluation on Diabetes Prediction Dataset**

#### Dataset Origin: https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset

### Dataset Description
The Diabetes prediction dataset is a collection of medical and demographic data from patients, along with their diabetes status (positive or negative). The data includes features such as age, gender, body mass index (BMI), hypertension, heart disease, smoking history, HbA1c level, and blood glucose level. This dataset can be used to build machine learning models to predict diabetes in patients based on their medical history and demographic information. This can be useful for healthcare professionals in identifying patients who may be at risk of developing diabetes and in developing personalized treatment plans. Additionally, the dataset can be used by researchers to explore the relationships between various medical and demographic factors and the likelihood of developing diabetes.


##### Result of the first 5 rows of the dataset:
<pre>
	gender	age	hypertension	heart_disease	smoking_history	bmi	HbA1c_level	blood_glucose_level	diabetes
0	Female	80.0	0		1		never		25.19	6.6		140			0
1	Female	54.0	0		0		No Info		27.32	6.6		80			0
2	Male	28.0	0		0		never		27.32	5.7		158			0
3	Female	36.0	0		0		current		23.45	5.0		155			0
4	Male	76.0	1		1		current		20.14	4.8		155			0
</pre>


##### More information about each column:
<pre>
RangeIndex: 100000 entries, 0 to 99999
Data columns (total 9 columns):
 #   Column               Non-Null Count   Dtype  
---  ------               --------------   -----  
 0   gender               100000 non-null  object 
 1   age                  100000 non-null  float64
 2   hypertension         100000 non-null  int64  
 3   heart_disease        100000 non-null  int64  
 4   smoking_history      100000 non-null  object 
 5   bmi                  100000 non-null  float64
 6   HbA1c_level          100000 non-null  float64
 7   blood_glucose_level  100000 non-null  int64  
 8   diabetes             100000 non-null  int64  
dtypes: float64(3), int64(4), object(2)
memory usage: 6.9+ MB
</pre>


### Result of Data Visualization Step

##### **Figure #01: Heatmap of Correlation Matrix**



##### **Figure #02: Scatter Plot of Age and BMI, Mark Heart Disease**



##### **Figure #03: Scatter Plot of Age and BMI, Mark Smoking History**



##### **Figure #04: Scatter Plot of Age and BMI, Mark Hypertension**



##### **Figure #05: Histogram and KDE Diagram of BMI, Diabetes Category**



##### **Figure #06: Histogram of Age, Diabetes Category**



##### **Figure #07: Histogram of Age, Hypertension Category**




##### **Figure #08: Histogram of Age, Heart Disease Category**



##### **Figure #09: Count Plot of Gender and Smoking Category**



##### **Figure #10: Bar Plot of Gender and Smoking Category**



### Data Preprocessing Step

1. Attribute Combination 
2. Column Transformer of categorical and numerical columns

For categorical columns, one-hot encoding is required.

For numerical columns, standard scaling is required.


### Model Evaluation Step
No model is tuned and they trained and evaluated with the default value of hyperparameters.


##### Logistic Regression: 
<pre>
Accuracy on seen data: 96.0840
Precision score on seen data: 0.8776
Recall score on seen data: 0.6246
AUC seen: 80.8256
----------------------------------------
Accuracy on unseen data: 96.0867
Precision score on seen data: 0.8811
Recall score on seen data: 0.6217
AUC unseen: 80.6984
</pre>


##### SGD Classification:
<pre>
Accuracy on seen data: 96.1280
Precision score on seen data: 0.8974
Recall score on seen data: 0.6128
AUC seen: 80.3137
----------------------------------------
Accuracy on unseen data: 96.0693
Precision score on seen data: 0.9069
Recall score on seen data: 0.5970
AUC unseen: 79.5671
</pre>



##### Support Vector Machine:
<pre>
Accuracy on seen data: 96.2133
Precision score on seen data: 0.9733
Recall score on seen data: 0.5683
AUC seen: 78.3452
----------------------------------------
Accuracy on unseen data: 96.1467
Precision score on seen data: 0.9686
Recall score on seen data: 0.5631
AUC unseen: 78.0730
</pre>



##### KNN:
<pre>
Accuracy on seen data: 96.9880
Precision score on seen data: 0.9532
Recall score on seen data: 0.6775
AUC seen: 83.7203
----------------------------------------
Accuracy on unseen data: 96.0360
Precision score on seen data: 0.8895
Recall score on seen data: 0.6072
AUC unseen: 80.0133
</pre>


##### Random Forest:
<pre>
Accuracy on seen data: 99.9320
Precision score on seen data: 0.9995
Recall score on seen data: 0.9924
AUC seen: 99.6199
----------------------------------------
Accuracy on unseen data: 97.0280
Precision score on seen data: 0.9467
Recall score on seen data: 0.6877
AUC unseen: 84.2067
</pre>


##### XGBoost:
<pre>
Accuracy on seen data: 97.2480
Precision score on seen data: 0.9890
Recall score on seen data: 0.6825
AUC seen: 84.0910
----------------------------------------
Accuracy on unseen data: 97.1987
Precision score on seen data: 0.9823
Recall score on seen data: 0.6814
AUC unseen: 84.0141
</pre>


### Fine-tune Step
After fine-tuning, I came up with these values for hyperparameters:
<pre>
{'max_depth': 3, 'max_features': 6, 'n_estimators': 100}
</pre>


### Accuracy on the Test Set
Finally, the accuracy on the test set is **97.116%**






