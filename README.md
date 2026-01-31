# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
## NAME: CH.V.S.DINESH KUMAR
## REG NO: 212224040055
```py
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
```
<img width="1029" height="843" alt="image" src="https://github.com/user-attachments/assets/a90ade1c-cc74-4108-911a-9e6d1fd47d67" />

```py
df.head()
```
<img width="1188" height="315" alt="image" src="https://github.com/user-attachments/assets/89f05f7e-af82-41ee-8efe-eecffcd09870" />

```py
df.tail()
```
<img width="1025" height="278" alt="image" src="https://github.com/user-attachments/assets/276b7d2e-25e3-4ef3-aad1-73b97b31c057" />

```c
df.info()
```
<img width="528" height="481" alt="image" src="https://github.com/user-attachments/assets/c4e99910-3753-4956-93d6-d066e96c257e" />

```c
df.describe()
```
<img width="997" height="466" alt="image" src="https://github.com/user-attachments/assets/b5e71e9b-fea1-4528-bcf6-8702ad7c2fe0" />

```c
df.isnull().sum()
```
<img width="258" height="337" alt="image" src="https://github.com/user-attachments/assets/eeb7e8bd-4947-4b30-8f6a-72945829ac02" />

```c
df.isnull().any()
```
<img width="245" height="332" alt="image" src="https://github.com/user-attachments/assets/a4bb3f34-6724-4d0f-bec6-7bd7efff8b7d" />

```c
df.dropna()
```
<img width="947" height="579" alt="image" src="https://github.com/user-attachments/assets/a9bab939-8ea5-4980-9272-63b7bc5b40e6" />

```c
df.fillna(0)
```

<img width="912" height="812" alt="image" src="https://github.com/user-attachments/assets/0ea9fbee-c237-44d4-bac3-f65bd1dd1eaa" />

```c
df.ffill()
```
<img width="931" height="812" alt="image" src="https://github.com/user-attachments/assets/d5562da7-6baa-4b35-9951-07d550169f08" />

```c
df.fillna({'GENDER':'MALE','NAME':'SRI'})
```
<img width="929" height="832" alt="image" src="https://github.com/user-attachments/assets/7a8d40c4-df3c-4653-ac0c-6629603a2008" />


```c
ir=pd.read_csv("iris.csv")
ir
```
<img width="603" height="524" alt="image" src="https://github.com/user-attachments/assets/c0a5946e-9c4f-49ef-b8ea-7a0569ff8a52" />

```c
ir.describe()
```
<img width="539" height="371" alt="image" src="https://github.com/user-attachments/assets/b4712824-88ec-4d7e-884f-8f501a4db367" />


```c
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
<img width="722" height="581" alt="image" src="https://github.com/user-attachments/assets/f47097e5-5830-4ee1-b30b-c8e4b34059b4" />


```c
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```
<img width="332" height="132" alt="image" src="https://github.com/user-attachments/assets/130e4930-a5f0-41db-8b67-9dcceb5c1b30" />

```c
ran=ir[((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="617" height="171" alt="image" src="https://github.com/user-attachments/assets/2d6ebd20-e87c-4d54-9b0a-b8c5178c287e" />

```c
ran=ir[~((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="598" height="301" alt="image" src="https://github.com/user-attachments/assets/99d951d0-2a71-4295-8a02-927c389f5833" />

```c
sns.boxplot(x='sepal_width',data=ran)
```
<img width="744" height="559" alt="image" src="https://github.com/user-attachments/assets/67a00927-17f8-43cc-bf49-15995258b591" />

```c
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir['petal_length']))
z
```
<img width="740" height="731" alt="image" src="https://github.com/user-attachments/assets/24ad3ea3-95b6-4a0d-b8d2-cb18bf02098e" />


```c
ir1=ir[z<3]
ir1
```
<img width="587" height="522" alt="image" src="https://github.com/user-attachments/assets/d41d5fe8-21e6-4036-b0ca-d5c6525c1168" />

# Result
```
    thus the given data successfully performed data cleaning and saved the cleaned data to a file
```
