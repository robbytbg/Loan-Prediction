
## Business Understanding

Upon receiving a loan application, the business must decide whether to approve the loan based on the applicant's profile. The bank's choice carries two different kinds of risks:

1\. false positive (Type I) Situation: Although the applicant defaults, the model approves the loan and indicates that the applicant will return it.

Impact: Should the applicant default, this could result in monetary loss for the organization.

2\. false negative (Type II) Situation: Although the application would have returned the loan, the model predicts that the applicant would default and be rejected.

Impact: The company loses out on a potentially lucrative customer as a result, which causes a decline in business.

## Business Objective

Objective: Using past data, create a machine learning model that predicts whether a customer's loan application will be approved or denied.

Key Steps:

1\. Preparing Data:

This procedure makes sure the dataset is optimized by eliminating columns that don't include any useful information. it helps to create a more useful and targeted dataset for further analysis.

2\. Feature Importance Analysis:

Examining the significance and effects of different aspects on the loan acceptance procedure is the focus of this investigation. An Exploratory Data Analysis (EDA) can offer important insights on the features of the dataset before this analysis.

3\. Model Development:

To prepare the dataset for train and evaluate machine learning algorithms, identifying trends and connections related to loan approval.

4\. Model Evaluation:

To guarantee accurate predictions, evaluate the model's performance using important metrics including accuracy, precision, recall, and F1-score.

## Preparing Data

1\. Loading the Dataset:

A pandas DataFrame (df variable) can be used to load a dataset from a CSV file using the 

pd.read_csv function. The location of the CSV file on the local computer is indicated by the file path.
```
df = pd.read\_csv('path.csv')
```
2\. Removing Columns with Only Missing Values:

a. Using the expression df.isnull(), the function finds the columns in the DataFrame (df) when all values are absent (NaN).all(). The null_columns variable contains these columns.

b. The DataFrame's columns containing all missing values are eliminated using the df.drop(null_columns, axis=1) method. Dropping columns is specified by the axis=1 argument.

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.004.png)

## Feature Importance Analysis

1\. Unique Identifiers Handling:

Checked the uniqueness of identifiers.

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.005.png)

2\. Categorical Variable Transformation:

Explored and transformed unique values in categorical columns. Replaced specific values in certain columns.

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.006.png)

3\. Handling Missing Values:

Explored and addressed missing values in specific columns.![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.007.png)

4\. Drop Unnecessary Columns:

Dropped unnecessary columns from the dataset.

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.008.png)

5\. Exploring and Transforming Numeric Variables:![ref2]

Checked for specific conditions in numeric columns. Transformed and extracted numeric values from specific columns.

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.009.png)

6\. Feature Engineering:

Created new boolean columns based on specific conditions. Cleaned and created new columns based on existing ones.![ref2]![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.010.png)

## Explanatory Data Analysis(EDA)

1\. Correlation matrix :

It helps us understand the linear relationships between pairs of numeric variables in a dataset Usage :

a. Identifying Relationships
b. Multicollinearity Detection
c. Feature Selection

2\. Dropping Highly Correlated Features

The process of dropping highly correlated features involves removing one of the two correlated variables to address multicollinearity.![ref2]

Usage :

a. Improved Model Stability
b. Enhanced Model Interpretability
c. Reduced Overfitting
d. Computational Efficiency

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.011.png)

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.012.png)

3\. Visualization :

the goal is to interact with the data, discover patterns, and make informed decisions about subsequent analysis and modeling steps![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.013.jpeg)

## Model Development

1\. Label Encoding:

   Label Encoding is a technique used to convert categorical variables into numerical format, which is essential for feeding data into machine learning models. Label Encoding assumes an ordinal relationship between categories, as it assigns integers.![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.014.png)![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.015.png)![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.016.png)

2\. One-Hot Encoding:

   One-Hot Encoding is used when dealing with categorical variables with more than two categories. It creates binary columns for each category, representing the presence or absence of that category for each observation.![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.017.png)![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.018.png)![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.019.png)

3\. Standard Scaling:

   Standard Scaling (or Z-score normalization) is applied to numeric features to ensure that they have a mean of 0 and a standard deviation of 1. This scaling is particularly important for models that rely on distance metrics, It prevents features with larger scales from dominating the learning process.

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.020.png)

4\. DataFrame Splitting:

   To evaluate the model's performance effectively, the dataset is split into training and testing sets. This step ensures that the model is trained on a portion of the data and evaluated on unseen data, providing insights into its generalization capabilities.

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.021.png)


## Model Evaluation

1\. Performance Measurement

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.022.png) ![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.023.png)

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.024.png)


2\. cross-validation:

a. Its primary purpose is to assess how well a model will generalize to an independent dataset

![](Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.025.png)

3\. Output summarization

1. Model Selection:
   1. Considering the metrics, Random Forest and XGBoost appear promising for predicting loan default.
1. Confidence in Model:

i. The models demonstrate strong accuracy and balanced precision-recall trade-offs, instilling 

confidence in their ability to make reliable predictions.

[ref1]: Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.001.png
[ref2]: Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.002.png
[ref3]: Aspose.Words.099c35ca-c154-49a0-ac1d-53091fb8b316.003.png
