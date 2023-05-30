# Ex-04-Multivariate-Analysis

##AIM:

To perform Multivariate EDA on the given data set.

##EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

##ALGORITHM:

##STEP 1

Import the built libraries required to perform EDA and outlier removal.

##STEP 2

Read the given csv file.

##STEP 3

Convert the file into a dataframe and get information of the data.

##STEP 4

Return the objects containing counts of unique values using (value_counts()).

##STEP 5

Plot the counts in the form of Histogram or Bar Graph.

##STEP 6

Use seaborn the bar graph comparison of data can be viewed.

##STEP 7

Find the pairwise correlation of all columns in the dataframe.corr() .

##STEP 8

Save the final data set into the file.

##PROGRAM:

NAME:Nivetha.A

REG NO:212222230101

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Category'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

data.corr()

sns.heatmap(data.corr(),annot=True)

##OUTPUT:

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/69cc39c4-1fa7-4542-8140-7108f799e77c)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/40878354-f742-47db-9db5-2a46251c533e)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/85488827-9451-44f3-9062-75d07fca3ffc)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/3a192ea1-88bd-4a8a-aa98-b39904f7f5ef)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/1bb5485d-f07f-4020-b5c6-9276852910cb)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/f1dd7309-b79a-4288-9c1f-1acf861d82d3)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/c2ab2cfc-ef41-4eeb-8446-ab08f0fb9dd8)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/45a6c912-ae83-4734-9861-f5d04c34b28f)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/0c4a0411-2c92-49da-900e-60a48c81403b)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/6381f881-e0b7-4c77-a10e-f74f8a6b5e87)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/78eecf4c-de4d-42b2-9ce5-af4802965e58)

![image](https://github.com/nivetharajaa/Ex-04-Multivariate-Analysis/assets/120543388/3dcd3e07-e14b-41b9-98eb-1d95a27c5781)

##RESULT

Hence The Performance of the Multivariate EDA on the given data set is verified.













