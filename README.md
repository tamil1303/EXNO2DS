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

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("/content/titanic_dataset.csv")
```
```
dt
```
![image](https://github.com/user-attachments/assets/d3d1579b-0e6b-4a6e-9a4d-8504cec089e6)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/3e406f89-aea5-41ec-b2f9-392807bc98f2)
```
dt.set_index("PassengerId",inplace=True)

dt
```
![image](https://github.com/user-attachments/assets/69463707-c2b9-4596-af32-7283ea2cfb31)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/da66fd06-b2ef-454a-bb24-c0fb1137bb14)
```
dt.describe()
```
![image](https://github.com/user-attachments/assets/05cb9b79-302a-4a1e-a084-598858c8bdf3)
```
dt.head()
```
![image](https://github.com/user-attachments/assets/64acda09-1bf4-429c-8f99-032e6123926c)
```
dt.tail()
```
![image](https://github.com/user-attachments/assets/c074fa86-974e-4d49-82e2-c07b94c8344e)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/f2b58216-f442-41a1-b78a-6bb5091a6ba5)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/9c470952-1876-4b55-bab7-9e7671fc10ff)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/c37c6ab8-f692-4c24-932e-ca4d82c7daf3)
```
#univariate analysis
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/27c2d1cc-848c-482b-ae35-648a3dbc7a87)
```
dt
```
![image](https://github.com/user-attachments/assets/22c59c40-80ba-4cbd-868f-c6ad2b236f25)
```
dt.Pclass .unique()
```
![image](https://github.com/user-attachments/assets/ddedf046-a2c8-490b-a2b7-0d20579311ed)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/82923cb8-874b-49cf-85b2-8114d18b1512)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/c2d1753c-6c19-43ec-a47c-75dc62b886f0)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/7dfa3afc-c119-48a3-9e67-f6f68ec4afd5)
```
sns.catplot(col="Survived",x="Sex",hue="Pclass",kind="count",data=dt)
```
![image](https://github.com/user-attachments/assets/17dcdd64-d09d-4661-9b18-95194edf64d5)
```
data=dt[['Survived','Pclass','Age','Fare','Parch']]
```
```
correlation_matrix=data.corr()
sns.heatmap(correlation_matrix,annot=True)
```
![image](https://github.com/user-attachments/assets/c836ec94-a420-4aed-b497-92281d800013)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/c8a1c8b2-7352-43ef-aa41-edfb7a28eeeb)
```
import seaborn as sns
```
```
sns.catplot(x="Sex",col="Survived",kind="count",data=dt,height=5,aspect=0.7)
```
![image](https://github.com/user-attachments/assets/0974c05b-935a-45b4-8e06-8952fd7b7dc7)
```
sns.catplot(x="Survived",hue="Sex",kind="count",data=dt)
```
![image](https://github.com/user-attachments/assets/8db5af9f-55d0-4912-92b3-9a5328afb834)
```
fig,ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=dt)
```
![image](https://github.com/user-attachments/assets/2d312f60-f6d3-4abc-bda4-3dc41daec7a8)


     

# RESULT
       Thus Exploratory Data Analysis is performed on the given data set.
