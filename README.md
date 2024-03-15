# EX.NO-2DS
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
NAME : Haarish V
Reg No : 212223230067
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic.csv")
dt
```
![Screenshot 2024-03-15 160600](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/8f95472c-3c25-46de-9657-0110c9bac691)


```
dt.info()
```
![Screenshot 2024-03-15 160609](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/1ce4e7f8-84ac-4310-9795-8344ff5869a2)


```
dt.set_index('PassengerId',inplace=True)
dt.describe()
```

![Screenshot 2024-03-15 160621](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/7f22c50e-effb-43ff-8850-f6ad55ce6fbc)


```
dt.shape
```

![Screenshot 2024-03-15 160630](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/4d08efc6-eb82-4b0d-93d8-6904fabf617f)


```
dt.nunique()
```

![Screenshot 2024-03-15 160712](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/361f02d0-6548-4f4d-8659-ec7bb124d7cc)


```
dt["Survived"].value_counts()
```

![Screenshot 2024-03-15 160717](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/91f257cc-f1a4-4edc-96ae-4e155eb48f7d)


```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

![Screenshot 2024-03-15 160722](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/04765267-626a-4848-8b18-a2fddcfad042)


```
sns.countplot(data=dt,x="Survived")
```

![Screenshot 2024-03-15 160730](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/152b59aa-8f2f-44dc-b0c7-59e387e32dd4)

```
dt.Pclass.unique()
```

![Screenshot 2024-03-15 160745](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/c8c36b6f-03b4-452c-8a87-3c8524834593)


```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

![Screenshot 2024-03-15 160755](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/f5b0459c-503e-4aed-9ade-57c6c06ff0a7)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

![Screenshot 2024-03-15 160804](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/11174263-c928-4c14-a3f8-cd9973ea58b9)


```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```

![Screenshot 2024-03-15 160812](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/0196f6fc-927d-4b93-966d-beeb44b1e1e7)


```
dt.boxplot(column="Age",by="Survived")
```

![Screenshot 2024-03-15 160820](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/84cbc513-b7fd-42e9-99c0-cfbc3d8da0c5)


```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![Screenshot 2024-03-15 160826](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/5c582245-c2d9-4cb3-be12-1f668f57b813)


```
sns.jointplot(x=dt["Age"],y=dt["Fare"],data=dt)
```

![Screenshot 2024-03-15 160833](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/79eb1208-b9b6-4d07-8cd6-cb5ed4aa8982)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```

![Screenshot 2024-03-15 160843](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/831b45be-c200-4d48-a129-803641d98d24)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![Screenshot 2024-03-15 160852](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/d77c7125-ec31-4601-bb77-78f299ceed89)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![Screenshot 2024-03-15 160902](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/4758a059-5dc2-463c-8cdb-4ee6ba15d2ba)

```
sns.pairplot(dt)
```

![Screenshot 2024-03-15 161018](https://github.com/Haarish-23013963/EXNO2DS/assets/147139700/806e5273-f32c-46bd-866f-c62d65bd277d)

# RESULT
Thus,Data Analyzing of the given dataset was successful.
