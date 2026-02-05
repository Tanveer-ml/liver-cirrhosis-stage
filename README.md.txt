Liver Cirrhosis Stage Prediction:

End to end Machine Learning Project

Liver Cirrhosis

Liver cirrhosis is a chronic disease that progresses through different stages.
Early and accurate stage prediction helps in better treatment planning.

Goal: Predict the stage of liver cirrhosis using clinical features.

Dataset Overview: -
The data provided is sourced from a Mayo Clinic study on primary biliary cirrhosis (PBC) of the liver carried out from 1974 to 1984.
Contains numerical and categorical features

Type of ML Task:
•	Supervised Learning
•	Classification (multi-class)

Target variable: Liver Cirrhosis Stage (1,2,3)

Cirrhosis Stages (Target Definition)

Cirrhosis is commonly categorized into the following stages: 1,2 or 3.

Description of columns: 

N_Days	 Number of days between registration and the earlier of death, transplantation, or study analysis time in 1986
Status	status of the patient C (censored), CL (censored due to liver tx), or D (death)
Drug	type of drug D-penicillamine or placebo
Age	age in days
Sex	M (male) or F (female)
Ascites	presence of ascites N (No) or Y (Yes)
Hepatomegaly	presence of hepatomegaly N (No) or Y (Yes)
Spiders	presence of spiders N (No) or Y (Yes)
Edema	presence of edema N (no edema and no diuretic therapy for edema), S (edema
present without diuretics, or edema resolved by diuretics), or Y (edema despite diuretic
therapy)

Bilirubin	serum bilirubin in [mg/dl]
Cholesterol	serum cholesterol in [mg/dl]
Albumin	albumin in [gm/dl]
Copper	urine copper in [ug/day]
Alk_Phos	alkaline phosphatase in [U/liter]
SGOT	SGOT in [U/ml] (a liver enzyme)
Tryglicerides	triglicerides in [mg/dl]

Platelets	platelets per cubic [ml/1000]
Prothrombin	prothrombin time in seconds [s]
Stage	histologic stage of disease (1, 2, or 3 )



Steps in building the model:

1.	Loading the data

2.	Importing the libraries.

3.	Exploratory Data Analysis.

4.	Data Processing.

5.	Model Training.

6.	Evaluating Metrics.

7.	Comparing the models

8.	Making predictions on new data.


Exploratory Data Analysis (EDA)

EDA is performed to understand the data distribution, relationships between features and class balance before model training.

1.	Firstly, I plotted count plot to find the distribution of target column i.e Stage and found it was uniformly distributed.

2.	Secondly, I plotted the histogram plot of age_years column to find the distribution of age, and it was found that most patients were middle aged to elderly.

3.	Thirdly found the distribution of Numerical features, it helps us to find the outliers and skewness in the data.

4.	Then, I found the correlation heatmap and found the correlation among various features. And from the correlation bilirubin was largely impacting the liver cirrhosis stage.

5.	At last, I found the relationship between the key feature(bilirubin) levels increase with disease severity.

Data Preprocessing

Performed Data Cleaning: -Removed rows with missing target.

Handling the categorical columns and applied the label encoding technique using the LabelEncoder () functionality of scikit-learn library.

Also, Handled the numerical columns to bring them to common scale in such a way to have mean = 0 and standard deviation = 1using StandardScaler () functionality of the scikit-learn library.

Handling missing values: - 

Median for numerical.

Mode for categorical.


 

Feature scaling

Splitted the data into training and test using the train_test_split functionality of the scikit-learn. Splitted the data in such a way to have 80% of the data as training data and 20% as test data.

Used stratify = y to keep the same class distribution of stage in both training and test.

 




Models Used and evaluation metrics:

	Accuracy	Precision	Recall	F1-score



Logistic Regression	57.84%	Class 1	0.57	0.59	0.58

		Class 2	0.51	0.47	0.49

		Class 3	0.64	0.67	0.66

Decision Tree Classifier	91.18%	Class 1	0.91	0.90	0.90

		Class 2	0.89	0.91	0.90

		Class 3	0.93	0.93	0.93

Random Forest Classifier	95.2%	Class 1	0.96	0.93	0.95

		Class 2	0.93	0.95	0.94


		Class 3	0.96	0.97	0.97


Support Vector Classifier	81.7%	Class 1	0.82	0.79	0.80

		Class 2	0.76	0.82	0.78

		Class 3	0.89	0.84	0.86

K-Nearest Neighbours	99.74%	Class 1	0.87	0.89	0.88

		Class 2	0.87	0.88	0.87

		Class 3	0.92	0.90	0.91













After finding the evaluation metrics then I compared all the models and found the best one and stored that in result_df.

Best Model Performance

The model which performed best was the: RandomForestClassifier.


Prediction on New Data

New patient data passed through same preprocessing as used in the model training.

Model outputs predicted cirrhosis stage.

Conclusion

Built a complete end-to-end ML model.

Model can assist doctors in early diagnosis.












