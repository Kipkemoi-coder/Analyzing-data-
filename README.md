# Analyzing-data-
import pandas as pd
import matplotlib.pylot as plt
import seaborn as sns

# Task 1 load and explore the Dataset
try:
# Load the dataset
df=pd.read_csv('sales_data.csv') #Replace 'sales_data.csv' with your dataset file
# display the first few rows
print(df.head)()
# check data types and missing values
print("\nData types of each column:")
print(df.dtypes)

print("\Missing values in each column:")
print(df.isnull().sum())
# clean the dataset by filling the missing values(if any)
# for example, fill missing numerical values with the mean
for column in df.select_dtypes(include=['number']):
df[column].fillna(df[column].mean(), inplace=True)
#or, drop rows with any missing values
#df.dropna(inplace=true)

print("\nMissing values after cleaning:")
print(df.isnull().sum())
except FileNotFoundError:
print("Error: The file 'sales_data.csv' was not found.Please make sure the file exists and the path is correct.")
except Exception as e:
print(f"An eror occured:{e}")
# Task 2: Basic Data Analysis
try:
# Compute basic statistics of numerical columns
print("\nBasic statistics of numerical columns
print(df.describe())
# Group by a categorical column and compute the mean of a numerical column for each group
if 'Region' in df.columns and'Sales' in df.columns:
grouped_data=df.groupby('Region')['Sales'].mean()
else:
print("\n'Region' or 'Sales' column not found.Please ensure your dataset contains these columns, or modify the code accordingly.")
# identify any patterns or interesting findings from your analysis.
 for example,you might notice that certain regions have higher average sales than others.
 except Exception as e:
 print(f"An error occored during data analysis: {e}")
 
