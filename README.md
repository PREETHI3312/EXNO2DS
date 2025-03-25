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
df=pd.read_csv('titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/8dd5efa2-943e-4233-87ec-74460264d2d9)
```
df.info()
```
![image](https://github.com/user-attachments/assets/971cdfad-8ad9-4aae-a5ea-f6acce2c96c2)
```
df.shape
```
![image](https://github.com/user-attachments/assets/25d935aa-b33f-4cff-aa93-b6f119f83c3a)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/96ec43b9-b486-4806-b25f-b700f5f8cb1a)
```
df.shape
```
![image](https://github.com/user-attachments/assets/82481e83-cfd2-4401-8cd4-df9db38aa798)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/b026e188-77ad-4ca0-8ab9-375c005e24ea)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/b4af66d4-b31a-4736-b6d7-e859e3005e86)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/990c1c14-6588-4ae1-9b5d-31b538d3ebc1)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/36cd57b1-d08c-428f-a163-3ec6b1596e62)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/0eda2988-795b-41f5-970d-2feb81a450fc)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/ccf3883e-d112-408c-a747-f25e8672931b)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/22dc8754-3a93-4a5f-9955-76160c9668e2)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/ae9d06ff-062c-408c-b5ea-80c06a57e5d2)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/62dcb458-c317-4493-baf7-d2f6222fd380)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/2487d714-f82b-423b-8169-c686534faaab)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/d35b0893-85a3-46b8-a187-58dfe9031022)
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/68851f82-2edf-472d-8352-f226d50d7f1b)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/17d8907b-a1dc-4512-a613-f8fdd95e2cbc)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/ab046219-1dfd-4381-b76a-35caf2974592)
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```



# RESULT
       Thus this dataset has been completely analysed successfully
