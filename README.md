# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING 

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Read the dataset
dt = pd.read_csv("titanic_dataset.csv")

# Display number of rows and columns
num_rows, num_cols = dt.shape
print(f"Number of rows: {num_rows}")
print(f"Number of columns: {num_cols}")

# Set PassengerId as index column
dt.set_index('PassengerId', inplace=True)

# Describe the dataset
dt.describe()

# Categorical data analysis
# Using value_counts() to perform categorical analysis
categorical_columns = ['Sex', 'Pclass', 'Embarked']
for col in categorical_columns:
    print(f"Value counts for column {col}:")
    print(dt[col].value_counts())
    print("\n")

# Univariate analysis
# Countplot for 'Survived' column
plt.figure(figsize=(8,5))
sns.countplot(x='Survived', data=dt)
plt.title('Survival Count')
plt.xlabel('Survived')
plt.ylabel('Count')
plt.show()

# Identify unique values in "Pclass" column
unique_pclass = dt['Pclass'].unique()
print("Unique values in 'Pclass' column:", unique_pclass)

# Renaming the 'Sex' column to 'Gender'
dt.rename(columns={'Sex': 'Gender'}, inplace=True)

# Bivariate analysis
# Catplot for bivariate analysis
plt.figure(figsize=(8,5))
sns.catplot(x='Survived', hue='Pclass', col='Gender', kind='count', data=dt)
plt.show()

# Boxplot for analyzing 'Age' and 'Survived' columns
plt.figure(figsize=(8,5))
sns.boxplot(x='Survived', y='Age', data=dt)
plt.title('Age vs Survived')
plt.show()

# Multivariate analysis
# Boxplot for analyzing 'Pclass', 'Age', and 'Gender'
plt.figure(figsize=(10,6))
sns.boxplot(x='Pclass', y='Age', hue='Gender', data=dt)
plt.title('Age distribution across Pclass and Gender')
plt.show()

# Catplot for analyzing 'Pclass', 'Survived', and 'Gender'
plt.figure(figsize=(10,6))
sns.catplot(x='Pclass', hue='Survived', col='Gender', kind='count', data=dt)
plt.show()

# Heatmap and pairplot
# Heatmap for correlation
plt.figure(figsize=(10,6))
sns.heatmap(dt.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Heatmap')
plt.show()

# Pairplot for exploring relationships between variables
sns.pairplot(dt)
plt.title('Pairplot of the Dataset')
plt.show()

```
### OUTPUT
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/445671d9-94c6-442b-8600-cc8325049db8)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/d7ac57bf-476b-4c8c-a1a6-76337f3cb454)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/56184eef-cd89-45af-ac32-157aa3362fce)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/1ec9aa9b-a1d1-4786-8965-4baee10c7370)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/895ca8a4-3326-4cee-8f30-37e430966d69)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/ad65da82-bfb3-4871-a989-67266f67e66d)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/fde44a6a-3036-43b4-b96f-001b9991a62c)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/b8b26d3d-60a7-4d27-9c2a-4e1228dd9cab)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/eeeb5aea-5eb3-4423-a35d-67f40e382eb1)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/d033f3fd-de8b-4938-bc6f-b95d22eea257)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/7c4a0f44-fae9-44bc-b1cb-7f1d7fb06f12)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/6d6ed3a5-30d2-4888-aafa-c13622b94b1c)
![Screenshot 2024-03-15 161144](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/f8d0fef9-c6ac-444f-9660-89ef93756834)
![image](https://github.com/bharathganeshsivasankaran/EXNO2DS/assets/119478098/93684c09-533e-401b-9c56-06bc9cc61c8a)









        
# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
