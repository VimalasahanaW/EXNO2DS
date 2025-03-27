# EXNO2DS
# Name: VIMALA SAHANA W
# REG.NO: 212223040241
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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2025-03-27 112134](https://github.com/user-attachments/assets/53942355-f345-4d98-b06d-247116ef5e87)
```
df.info()
```
![Screenshot 2025-03-27 112241](https://github.com/user-attachments/assets/74afa955-67cb-4bf9-8747-3158c03e9ec2)
```
df.shape
```
![Screenshot 2025-03-27 112326](https://github.com/user-attachments/assets/33eafb81-6ff5-42d4-8edb-1dcc41a44ba2)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2025-03-27 112427](https://github.com/user-attachments/assets/37274afc-8f5a-47f8-8c3c-feefa84555f1)
```
df.shape
```
![Screenshot 2025-03-27 112447](https://github.com/user-attachments/assets/8f65171b-7c0b-46a1-aeac-7ce233c326b6)
```
df.nunique()
```
![Screenshot 2025-03-27 112550](https://github.com/user-attachments/assets/3db3ff93-c1cd-450d-a6f8-e5ed81c3b860)
```
df["Survived"].value_counts()
```
![Screenshot 2025-03-27 112633](https://github.com/user-attachments/assets/2268537f-90d7-4e3a-9be1-6813aeab7f5a)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-27 112719](https://github.com/user-attachments/assets/7eca56b9-fe81-409f-b362-e3fe4132cd2e)
```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2025-03-27 112805](https://github.com/user-attachments/assets/4b1a0758-1543-43ce-ba98-9d27316945fc)
```
df
```
![Screenshot 2025-03-27 112844](https://github.com/user-attachments/assets/fb090b35-1fcc-4857-9207-e96a7e4533b1)
```
df.Pclass.unique()
```
![Screenshot 2025-03-27 112924](https://github.com/user-attachments/assets/eae0608c-c2cd-426f-a775-7026d5a05c8e)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2025-03-27 113015](https://github.com/user-attachments/assets/4fcf4909-c81a-4147-bc8f-a083b00edb6f)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2025-03-27 113102](https://github.com/user-attachments/assets/875cf7ab-dd63-4796-b1c6-052edb7d05da)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2025-03-27 113145](https://github.com/user-attachments/assets/fac147f6-e3d5-4b54-939f-8845649066b0)
```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-27 113227](https://github.com/user-attachments/assets/8303f338-f830-40dc-8dea-8b8549a164d5)
```
sns.scatterplot(x=df["Age"],y=df['Fare'])
```
![Screenshot 2025-03-27 113313](https://github.com/user-attachments/assets/9f3819ff-20fa-4ae5-848d-d7aec9253855)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2025-03-27 113450](https://github.com/user-attachments/assets/399ef0ba-5a9b-484e-b11a-d384d3e5a039)
```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y="Age",hue="Gender",data=df)
```
![Screenshot 2025-03-27 113527](https://github.com/user-attachments/assets/5088b793-e2c3-4204-b647-2b9604bec5ad)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-03-27 113609](https://github.com/user-attachments/assets/eef2dc6e-08e2-46fa-b3c1-7db72ccc0042)
```
df_numeric=df.select_dtypes(include=['number'])
corr=df_numeric.corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2025-03-27 113656](https://github.com/user-attachments/assets/f41f8cc4-b21c-4277-9119-0a61720ded34)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/c8edf005-3413-4b11-80d3-daaeed091f75)



# RESULT:
       We have performed Exploratory Data Analysis on the given data set successfully.
