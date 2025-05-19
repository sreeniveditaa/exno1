# Exno:1
Data Cleaning Process
### Name : SREE NIVEDITAA SARAVANAN
### REG. NO : 212223230213

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

```
import pandas as pd
df = pd.read_csv("Data_set.csv")
df
```
![{47177384-99EC-44C0-8D86-15C7089185AB}](https://github.com/user-attachments/assets/3fc73064-d7bd-4536-b936-9bc477b63918)

```
df.describe()
```
![{94FA9ABC-3671-4021-B3B2-5283CD2AA07B}](https://github.com/user-attachments/assets/a2f22836-1941-4551-94ee-065219b3d765)

```
df.info()
```
![image](https://github.com/user-attachments/assets/5fd60541-9d15-4222-8b43-1c3a912b1d34)

```
df.head()
```
![{9A87CF8E-CBB4-4BBB-8AFA-1C2CFA389D37}](https://github.com/user-attachments/assets/b2c00f81-cd9a-4c5c-9862-a7dc11ba653a)

```
df.tail()
```
![image](https://github.com/user-attachments/assets/8ace75e1-96c6-4c60-a5c4-744d982f8839)

```
df.isnull()
```
![image](https://github.com/user-attachments/assets/ef471b4f-c5ec-4095-97a7-14da223a1682)

```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/78d422de-1de5-4b7d-9f26-76522e09d5c0)

```
df.notnull()
```
![image](https://github.com/user-attachments/assets/6aca0466-3cc4-41ac-a660-7282da9cc767)

```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/eed410d7-0693-48e6-be97-4e66c162d0dc)

```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/dbee93df-91aa-4b07-bc54-7576e4cf6c43)

```
df.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/2b011469-3fbe-4d25-9252-ad5508d8b9f3)

```
df.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/9c9fd14c-f090-4c4e-9ba8-6bca6f2c3f0a)

```
df['watchers'].fillna(value=df['watchers'].mean())
```
![image](https://github.com/user-attachments/assets/f78e8100-39e2-4268-ac9a-c411a7967c22)

```
df['watchers'].fillna(value=df['watchers'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/35a001e3-f336-4e54-a67f-b0d69644b03e)

```
df['num_episodes'].fillna(value=df['num_episodes'].mean())
```
![image](https://github.com/user-attachments/assets/1683e943-0926-4fe6-9f65-4be14e7a04a6)

```
df['num_episodes'].fillna(value=df['num_episodes'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/d4cf953c-8801-4944-b8a2-0ef755b23bb8)

```
df['rating'].fillna(value=df['rating'].mean())
```
![image](https://github.com/user-attachments/assets/8d85cdc5-7547-4423-8b1c-07159d43da81)

```
df['rating'].fillna(value=df['rating'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/4c4f07b7-0087-4519-b539-40645ecbd14c)

```
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean())
```
![image](https://github.com/user-attachments/assets/c48569d7-e866-475a-bcd9-620de8421c54)

```
df['current_overall_rank'].fillna(value=df['current_overall_rank'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/43d2141e-05db-4821-ae1c-cbd242bf815c)

```
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
```
![image](https://github.com/user-attachments/assets/c8af7214-6461-44a2-9829-ab893758b5c1)

```
df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean(),inplace=True)
df
```
![image](https://github.com/user-attachments/assets/b9ff563a-264d-4437-9729-b444247dba62)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/user-attachments/assets/d4a75341-d165-4a78-9b8e-b34a46842f3b)

```
sns.boxplot(data=af)
```
![image](https://github.com/user-attachments/assets/ea83effd-eef5-4bc4-9fe5-8b6a01b92463)

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/eaf0233f-6e71-41fb-a707-0b30d9bee427)

```
lb=q1-1.5*iqr
ub=q3+1.5*iqr
lb
```
![image](https://github.com/user-attachments/assets/1763332c-5535-446b-a414-bd0856eb65d1)

```
ub
```
![image](https://github.com/user-attachments/assets/00aedc3d-a1d8-4c0b-8740-e0780e77f0af)

```
af=af[((af>=lb)&(af<=ub))]
af
```
![image](https://github.com/user-attachments/assets/cef36968-7068-4f3e-a218-409477258daf)

```
af.dropna()
```
![image](https://github.com/user-attachments/assets/f128107c-d9fb-4b96-a8b6-75441320c667)

```
sns.boxplot(data=af)
```
![image](https://github.com/user-attachments/assets/2046dbd0-21fc-49f3-87c1-7aa386a2bb82)

```
from scipy import stats
import numpy as np
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![image](https://github.com/user-attachments/assets/ffe0310b-b18c-4743-a124-28e375598a32)

```
val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,258]

out=[]
def d_o(val):
    ts=3
    m=np.mean(val)
    sd=np.std(val)
    for i in val:
        z=(i-m)/sd
        if np.abs(z)>ts:
            out.append(i)
    return out

op=d_o(val)
op
```
![image](https://github.com/user-attachments/assets/e2c55e24-83fc-4a13-9b7d-df1c574cf7a2)




# Result
Thus, the Data Cleaning Process is executed Successfully.
