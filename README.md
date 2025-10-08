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
 df=pd.read_csv("/content/titanic_dataset.csv")
 df
```
<img width="1129" height="383" alt="image" src="https://github.com/user-attachments/assets/19e8cf56-9846-4487-aed7-2bc7a40bdbfd" />

```
df.info()
```

<img width="613" height="594" alt="image" src="https://github.com/user-attachments/assets/36c78e7b-1f36-4a7b-aead-fbf5a9ad53c3" />

```
df.describe()
```

<img width="707" height="263" alt="image" src="https://github.com/user-attachments/assets/3a5c3bfe-1090-4e55-bfa7-82a75f419145" />


```
df.dtypes
```

<img width="178" height="423" alt="image" src="https://github.com/user-attachments/assets/55a00ac9-fcbc-481f-87b6-3d0697d0fb41" />


```
df.shape
```

<img width="83" height="30" alt="image" src="https://github.com/user-attachments/assets/73c6fc31-7b49-4945-940a-2f6ee523b935" />

```
df.value_counts()
```

<img width="1139" height="441" alt="image" src="https://github.com/user-attachments/assets/bcd7fdd8-7a97-4f4b-b0e8-50b4ee34be61" />

```
df['Age'].value_counts()
```

<img width="129" height="456" alt="image" src="https://github.com/user-attachments/assets/116633e1-578a-4dd0-9f77-b5a449846fc0" />

```
df.set_index("PassengerId", inplace=True)
df
```

<img width="1080" height="418" alt="image" src="https://github.com/user-attachments/assets/00643d14-96a8-4f8d-a094-79e410733bfd" />

```
df.nunique()
```

<img width="120" height="384" alt="image" src="https://github.com/user-attachments/assets/295f95da-2983-4708-a081-af4903c7da1f" />

```
sns.countplot(data=df,x='Survived')
```


<img width="552" height="430" alt="image" src="https://github.com/user-attachments/assets/90b10708-2d61-43c2-a41d-d01166ae975f" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1081" height="424" alt="image" src="https://github.com/user-attachments/assets/28530cf3-afef-446d-97cc-64737e789c0a" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="684" height="491" alt="image" src="https://github.com/user-attachments/assets/968ffd0b-54ae-4404-b1bc-54d5869407ad" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="534" height="461" alt="image" src="https://github.com/user-attachments/assets/87c92c19-cc51-4ee2-9eb5-a8c3ae16d208" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```


<img width="546" height="435" alt="image" src="https://github.com/user-attachments/assets/bcbe79fe-b5ae-4eee-9dee-a943bf065319" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="653" height="432" alt="image" src="https://github.com/user-attachments/assets/a0e4553e-6f21-4d6c-b56f-720919c26540" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="545" height="417" alt="image" src="https://github.com/user-attachments/assets/06cc7901-b6b1-4824-aa3c-d2a4730efb18" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="1039" height="492" alt="image" src="https://github.com/user-attachments/assets/8020aafb-4816-4e11-8997-e2e2b16bd5dc" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```

<img width="994" height="489" alt="image" src="https://github.com/user-attachments/assets/77e0c21b-fc3d-4dbb-8ac1-39ce679a8f86" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="505" height="422" alt="image" src="https://github.com/user-attachments/assets/4b7c3772-9a65-436d-8ea5-fe273038bff5" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
<img width="509" height="420" alt="image" src="https://github.com/user-attachments/assets/cf515dad-f814-4948-bb58-87ae4c2822a1" />


























 



## RESULT
Thus the programs are executed successfully.

