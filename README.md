# Ex:05 Feature Generation

# AIM
To read the given data and perform  Feature Encoding & Scaling process and save the data to a file.


# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM

# STEP 1
Read the given Data

# STEP 2
Clean the Data Set using Data Cleaning Process

# STEP 3
Apply Feature Generation techniques to all the feature of the data set

# STEP 4
Save the data to the file

# CODE AND OUTPUT
```
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()

```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/5a9ed7ca-0242-49c9-887d-650bc6faa419)
```
df = pd.read_csv("bmi.csv")
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/161aae55-e30c-4c1d-a862-ceebec2bf55d)
```
from category_encoders import BinaryEncoder
e1 = BinaryEncoder()
bn = e1.fit_transform(df['Gender'])
df = pd.concat([df,bn],axis = 1)
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/ca7992ef-4a69-47ea-a11b-0c3efae7d0db)
```
from sklearn.preprocessing import RobustScaler
rs = RobustScaler()
df[['Height','Weight']] = rs.fit_transform(df[['Height','Weight']])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/b6f5c142-61d4-4b03-b878-41c4ef6be381)
```
from google.colab import files
upload = files.upload()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/3992b7fd-081a-41aa-964e-19f0c9a72e5a)
```
df = pd.read_csv("data.csv")
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/bfe12410-71a3-4b29-9b49-e2531df1a63d)
```
from sklearn.preprocessing import OrdinalEncoder,LabelEncoder,OneHotEncoder
data = ['Very Hot','Hot','Warm','Cold']
e1 = OrdinalEncoder(categories = [data])
df['Ord_1'] = e1.fit_transform(df[['Ord_1']])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/906a2d2f-d36f-469f-8592-84c2b439df1c)
```
data1 = ['High School','Diploma','Bachelors','Masters','PhD']
e1 = LabelEncoder()
df['Ord_2'] = e1.fit_transform(df['Ord_2'])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/2b0b03e5-b520-419c-b888-f5e4845adf84)
```
e2 = OneHotEncoder(sparse = False)
enc = pd.DataFrame(e2.fit_transform(df[['City']]))
df = pd.get_dummies(df,columns = ['City'])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/c322517f-0e18-4b8c-b563-5b3a588e8fa5)
```
from category_encoders import BinaryEncoder
e3 = BinaryEncoder()
bn = e3.fit_transform(df[['bin_1','bin_2']])
df = pd.concat([df,bn],axis = 1)
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/8a40edb3-ccb7-4097-ba39-9e2838c4671e)
```
from sklearn.preprocessing import MinMaxScaler
mm = MinMaxScaler()
df[['Ord_1','Ord_2']] = mm.fit_transform(df[['Ord_1','Ord_2']])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/0416d008-0d52-48d5-bc75-b16de95c9eea)
```
from google.colab import files
upload = files.upload()
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/03dfb5b7-8755-4f63-b145-0ec847a1b842)
```
df = pd.read_csv("Encoding Data.csv")
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/d5a53906-47c1-455e-a4ef-8ce8f8ee6c1c)
```
from sklearn.preprocessing import LabelEncoder,OneHotEncoder
data1 = ['Hot','Warm','Cold']
e1 = LabelEncoder()
df['ord_2'] = e1.fit_transform(df['ord_2'])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/6c0eae13-7769-4cd2-b351-87f278ec8d49)
```
e2 = OneHotEncoder(sparse = False)
enc = pd.DataFrame(e2.fit_transform(df[['nom_0']]))
df = pd.get_dummies(df,columns = ['nom_0'])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/990ecdc3-9488-4030-a1cc-94c4fe18694b)
```
from category_encoders import BinaryEncoder
e3 = BinaryEncoder()
bn = e3.fit_transform(df[['bin_1','bin_2']])
df = pd.concat([df,bn],axis = 1)
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/a46c9667-5a01-498e-beff-6d87e1b2daaa)
```
from sklearn.preprocessing import  StandardScaler
ss = StandardScaler()
df[['ord_2']] = ss.fit_transform(df[['ord_2']])
df
```
![image](https://github.com/Vaish-1011/ODD2023-Datascience-Ex-05/assets/135130074/8082656a-3ee1-4097-a835-001f40183765)


# RESULT
Feature Encoding process and Feature Scaling process is applied to the given data frame sucessfully.
