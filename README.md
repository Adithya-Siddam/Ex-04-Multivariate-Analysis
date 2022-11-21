# Ex-04-Multivariate-Analysis
# AIM
To perform Multivariate EDA on the given data set.

## Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM
# STEP 1
Import the built libraries required to perform EDA and outlier removal.

# STEP 2
Read the given csv file

# STEP 3
Convert the file into a dataframe and get information of the data.

# STEP 4
Return the objects containing counts of unique values using (value_counts()).

# STEP 5
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

# STEP 8
Save the final data set into the file

## CODE
~~~
Name : S Adithya Chowdary.
Register Number : 212221230100.
~~~
~~~
import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt
df = pd.read_csv("/content/SuperStore.csv")
df.head(10)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sbn.scatterplot(df['Postal Code'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sbn.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])
df.corr()
sbn.heatmap(df.corr(),annot=True)
~~~
## OUTPUT

# EDA - SuperStore.csv
![image](https://user-images.githubusercontent.com/93427248/203043312-bb047566-6ec4-4064-abeb-77d0bf5cce63.png)
# Displaying information about Dataset
![image](https://user-images.githubusercontent.com/93427248/203043656-83c6b4e1-d2cd-43e4-9217-b104e627c5b9.png)

# Checking the null values and Cleaning it
![image](https://user-images.githubusercontent.com/93427248/203043691-6bf73e37-a44b-4fe6-bae7-c78f666e7181.png)
# Displaying datatypes of each features
# Multivariate Analysis - Scatterplot
![image](https://user-images.githubusercontent.com/93427248/203043842-2586cd24-3847-499d-bf25-6211fa02f284.png)
# Multivariate Analysis - Barplot
![image](https://user-images.githubusercontent.com/93427248/203044227-75b23d65-88c1-4429-959e-d4bca52b6a7f.png)


# Correlation Coefficient Interpretation using HeatMap

## RESULT
Thus the program to perform EDA on the given data set is successfully executed.
