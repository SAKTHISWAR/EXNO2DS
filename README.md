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

### Name : SAKTHISWAR S
### Reg No : 212222230127

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![img](out.png)


```
dt.info()
```
![img](out1.png)

```
dt.shape
```
![img](out2.png)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![img](out3.png)


```
dt.nunique()
```
![img](out4.png)

```
dt["Survived"].value_counts()
```
![img](out5.png)


```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![img](out6.png)

```
sns.countplot(data=dt,x="Survived")
```
![img](out7.png)


```
dt
```
![img](out8.png)


```
dt.Pclass.unique()
```
![img](out9.png)


```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![img](out10.png)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![img](out11.png)


```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
![img](out12.png)


```
dt.boxplot(column="Age",by="Survived")
```
![img](out13.png)


```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![img](out14.png)


```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![img](out15.png)


```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![img](out16.png)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![img](out17.png)


```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![img](out18.png)


```
sns.pairplot(dt)
```
![img](out19.png)

# RESULT
       Thus, the Exploratory Data Analysis on the given data set was performed successfully. 
