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
```
```
import numpy as np
```
```
import matplotlib.pyplot as plt
```
```
import seaborn as sns
```
```
dt=pd.read_csv("titanic_dataset (1).csv")
dt
```
<img width="1556" height="578" alt="image" src="https://github.com/user-attachments/assets/aedba2dd-2391-4f2e-a064-d36862b7dfcf" />
```
dt.info()
```
<img width="638" height="539" alt="image" src="https://github.com/user-attachments/assets/b7a62e27-f3e8-42b0-9b3d-2a115de8211a" />
```
dt.shape
```
<img width="848" height="57" alt="image" src="https://github.com/user-attachments/assets/c13af260-cb04-4319-878d-630b799a9ac2" />
```
dt.reset_index(inplace=True)
display(dt.head())
```
<img width="1577" height="328" alt="image" src="https://github.com/user-attachments/assets/90407eab-ddcf-4625-b862-26b92b74f356" />
```
dt.nunique()
```
<img width="818" height="402" alt="image" src="https://github.com/user-attachments/assets/87d1f7c6-78d1-420e-a3e3-1f82f31833ea" />
```
dt["Survived"].value_counts()
```
<img width="836" height="108" alt="image" src="https://github.com/user-attachments/assets/73492334-f5d1-4683-bb83-663966c193ec" />

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
<img width="815" height="108" alt="image" src="https://github.com/user-attachments/assets/55c16e72-7d56-416b-aeb2-598ce89c585f" />
```
sns.countplot(data=dt,x="Survived")
```
<img width="1239" height="727" alt="image" src="https://github.com/user-attachments/assets/6387a1f2-1805-40d7-bb9f-ec14137fe9bd" />
```
dt
```
<img width="1700" height="616" alt="image" src="https://github.com/user-attachments/assets/0037f5df-364a-48c3-9e7b-eff382503fb0" />
```
dt.Pclass.unique()
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
<img width="850" height="547" alt="image" src="https://github.com/user-attachments/assets/45a22820-00c5-4db3-9389-4608466467b6" />
```
sns.catplot(x='Survived',hue='Gender',data=dt,kind="count")
```
<img width="863" height="660" alt="image" src="https://github.com/user-attachments/assets/7987c376-41ef-4639-aaed-7ec5f24153d4" />
```
dt.boxplot(column="Age",by="Survived")
```
<img width="846" height="629" alt="image" src="https://github.com/user-attachments/assets/f93954a1-db00-4e81-9e5f-d424af2e0e37" />
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
<img width="866" height="588" alt="image" src="https://github.com/user-attachments/assets/565af201-a0e9-4c90-8b31-3077782621ce" />
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
<img width="945" height="782" alt="image" src="https://github.com/user-attachments/assets/0133e919-5d15-464e-94bd-93039bdab160" />
```
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
<img width="1099" height="583" alt="image" src="https://github.com/user-attachments/assets/d9078341-50db-48b0-8816-fc2594a015f1" />
```
sns.catplot(data=dt,col="Survived",x="Gender",hue='Pclass',kind="count")
```
<img width="905" height="406" alt="image" src="https://github.com/user-attachments/assets/77c8c26c-60af-4546-92fb-b595d9d21918" />
```
corr=dt.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="923" height="703" alt="image" src="https://github.com/user-attachments/assets/a7210271-6281-4ff0-b2b7-d99d6ac29cf3" />



# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.

        
