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
REG NO: 212224040268
NAME  : RAMYA S
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset (2).csv")
dt
```
![Screenshot 2025-04-18 092359](https://github.com/user-attachments/assets/371a130f-79d2-4bcf-986b-20c8f71aaa8a)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/7826b285-c679-4cf0-8288-87416d06494b)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/b5037981-d9fa-43cd-a056-99acc643541d)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/33a80a02-a69d-41db-9c51-ceca9b378e9e)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/e0a822fa-8db2-4330-9263-fb3313173ed4)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/bd6bd981-d12d-4a8c-bec4-4a3547e11de2)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/0d371a53-338a-45ba-b995-b8713cfefb48)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/971d4514-eff8-4465-84e7-1d12ab19c45b)
```
dt
```
![image](https://github.com/user-attachments/assets/d1e9714e-27bf-4f73-bf98-9ea2b2a1d910)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/56131634-fe3c-48b0-9397-a365c5d74639)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/a422b80e-28f7-42b3-a92c-77f3a71eb9cb)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/786f7d4f-7959-46cb-ae5e-0abbc02f3bb3)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/0d0cbe12-d964-469d-bd77-f649c92897bb)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/d312e5f7-fbf2-4d06-92e7-e3aac2c9e347)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/38107187-2778-47a9-8e65-e5d01b88b18c)
```
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/5f6dd0bc-1faa-4ef2-8eb3-c8f26d2f7c6a)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/777de285-fef5-439c-aed7-69962bbc83d7)

```
numeric_dt = dt.select_dtypes(include=['int64','float64'])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/e881faf7-baae-47a1-bcb1-0a293150e55f)

```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/340c334d-e01e-4c5e-b02a-a5ee1796b7ca)
![image](https://github.com/user-attachments/assets/f0d31581-86de-411b-8e79-4ccab400a44f)
















# RESULT
  Exploratory Data Analysis on the given data set was performed successfully.       
