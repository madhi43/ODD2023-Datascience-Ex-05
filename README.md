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
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/1b88e38a-a2a2-4d90-be3e-d8108be70d22)
```
df['ord_2'].unique()
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/528e6bd4-b15d-4ad5-a432-9b0191507637)
```
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/37e9147e-297a-4800-b7d3-1991db7c7986)
```
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/2ef374ab-15b6-4c8b-86c4-16337919a524)
```
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/9407add1-b79b-4482-b013-b95c704f28e0)
```
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/daab7b30-79bf-4404-9f08-2dbc3e3df486)
```
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/07574905-b967-4f4c-a12e-b33e6b35fd6f)
```
df1['Ord_1'].unique()
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/35406f8a-ad96-4b72-878d-4ce982754ebc)
```
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/7f70b365-457e-46dd-96ae-f0185608a63b)
```
df1['Ord_2'].unique()
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/b82bcb1d-b655-4bd6-9fb3-cb8b100d3945)
```
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/577450ef-7bbf-46a0-8388-aee2ed8b5898)
```
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/23c68591-6b39-49a1-b8dd-1ed170473b35)
```
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/b6129e71-e29e-487f-a8a8-e14432bad0fb)
```
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/075be6ee-e715-4199-b4b1-0aa3800cd241)
```
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/d913d151-e22c-4375-b0e6-ca36d39d22e9)
```
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/fe285e8e-edfd-49bc-90a8-ce81bf3192ad)
```
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```
![image](https://github.com/madhi43/ODD2023-Datascience-Ex-05/assets/103943383/22806850-4957-4db7-88f2-b4a9ec0cab40)


# RESULT
Feature Encoding process and Feature Scaling process is applied to the given data frame sucessfully.
