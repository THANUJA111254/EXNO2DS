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
df=pd.read_csv("titanic_dataset.csv")
df
```



<img width="1484" height="577" alt="image" src="https://github.com/user-attachments/assets/af33cb3e-e563-4993-a0f4-dbaf89efc299" />




```
df.info()
```



<img width="476" height="433" alt="image" src="https://github.com/user-attachments/assets/ae33aa52-33d9-498c-b9a1-44d0176ae73b" />



```
df.describe()
```




<img width="907" height="371" alt="image" src="https://github.com/user-attachments/assets/f027135e-224b-4cbe-ba06-15a4429d2755" />




```
df.dtypes
```





<img width="308" height="1033" alt="image" src="https://github.com/user-attachments/assets/805fb957-a5f2-46b6-9c12-e90da88d936b" />




```
df.shape
```






<img width="115" height="38" alt="image" src="https://github.com/user-attachments/assets/217ed162-e9f1-4f93-aef5-cd617db37424" />



```
df.value_counts()
```




<img width="1636" height="608" alt="image" src="https://github.com/user-attachments/assets/b2485220-20ef-4f5f-ae83-93532a4c9f07" />




```
df['Age'].value_counts()
```




<img width="333" height="650" alt="image" src="https://github.com/user-attachments/assets/1931d724-2efb-482d-af14-242a93146b5c" />




```
df.nunique()
```




<img width="275" height="551" alt="image" src="https://github.com/user-attachments/assets/249593b5-37a8-416a-b2f2-b9a6d302ab5a" />





```
sns.countplot(data=df,x="Survived")
```








<img width="767" height="564" alt="image" src="https://github.com/user-attachments/assets/459b078a-ea84-4457-abf3-9f1c3c943a1b" />






```
df.Pclass.unique()
```






<img width="206" height="54" alt="image" src="https://github.com/user-attachments/assets/1128489f-f929-4abe-99e0-8a2da329306a" />





```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```











<img width="1535" height="550" alt="image" src="https://github.com/user-attachments/assets/65638c59-56ab-45e6-a86b-0ad9ac76e733" />



```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```









<img width="1039" height="655" alt="image" src="https://github.com/user-attachments/assets/d2255bf2-fc8e-4aba-9c3f-7eee471613b9" />






```
df.boxplot(column="Age",by="Survived")
```










<img width="786" height="572" alt="image" src="https://github.com/user-attachments/assets/d01a30b9-9780-4232-adbc-3e36c012b2ff" />






```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```









<img width="750" height="581" alt="image" src="https://github.com/user-attachments/assets/7b5b6e78-abd0-4641-a50a-ff1aa00f46b8" />




```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```










<img width="1023" height="581" alt="image" src="https://github.com/user-attachments/assets/44baeece-c762-4f4a-92cf-9a6941377152" />






```
import seaborn as sns
sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=df)
```










<img width="1415" height="644" alt="image" src="https://github.com/user-attachments/assets/5a31f5a0-d908-4eb4-be96-3f10f68779cb" />




```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```






<img width="1513" height="672" alt="image" src="https://github.com/user-attachments/assets/b4d598cd-9234-41cb-9c13-0ea40b397fd9" />


```
corr = df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```





<img width="746" height="565" alt="image" src="https://github.com/user-attachments/assets/a315ab14-d9cf-4188-bdf9-7571afde9f11" />




# RESULT
        The output has verified successfully.
