# Ex:05 Feature Generation
# AIM
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM
STEP 1 Read the given Data

STEP 2 Clean the Data Set using Data Cleaning Process

STEP 3 Apply Feature Generation techniques to all the feature of the data set

STEP 4 Save the data to the file

# PROGRAM
```
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/a0e2588a-295f-4343-9e02-b13b820cb5d2)
```
df['ord_2'].unique()
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/b04a9626-d825-4d4f-a19f-4f482a7796d2)
```
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/1c5c4c35-d681-4e2b-88b8-499441177e84)
```
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/68a9465a-23a5-4e5d-9cde-38c30e841c27)
```
!pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
be = BinaryEncoder()
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/e39a5a15-c6bf-4f49-91c2-cbb0338494df)
```
data = be.fit_transform(df['bin_1'])
df  = pd.concat([df,data],axis=1)
df
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/815198e8-e84d-4446-ac11-255a255d3143)
```
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df  = pd.concat([df,data],axis=1)
df
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/ae30bdd3-9e76-4488-bec0-1e5bbd314488)
```
import pandas as pd
df1 = pd.read_csv("data.csv")
df1.head()
```

![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/ff52cb97-3f3d-4b28-8cf8-d73d0e42fa41)
```
df1['Ord_1'].unique()
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/3c37f03d-4639-47ff-aa2b-0199a98e7932)
```
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df1['Ord_1']=en.fit_transform(df1[["Ord_1"]])
df1
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/ccf0d0b5-25ad-4e75-9148-d0f41ea05d90)
```
df1['Ord_2'].unique()
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/e599e54a-6cf0-4ed2-816c-9e7039d6e3ad)
```
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df1['Ord_2']=en.fit_transform(df1[["Ord_2"]])
df1
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/150ba5ce-a2b2-40d3-a54b-b1c6d5c25b19)
```
le = LabelEncoder()
df1['City'] = le.fit_transform(df1[["City"]])
df1
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/1c5a2195-393f-46db-b005-3dd284559a1c)
```
from category_encoders import BinaryEncoder
be = BinaryEncoder()
dat = be.fit_transform(df1['bin_1'])
df1  = pd.concat([df1,dat],axis=1)
df1
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/41e15f88-5af9-4f16-bd4a-97a4df97165e)
```
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df1['bin_2'])
df1  = pd.concat([df1,data1],axis=1)
df1
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/9b1002d0-783d-4e34-b30d-4377dcb34b6c)
```
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/b06d854e-753a-4d5b-a799-b99be6547577)
```
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/46849699-c700-487d-9615-c2406d8cce74)
```
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```
![image](https://github.com/Sathya-006/ODD2023-Datascience-Ex-05/assets/121661327/2f35e6b3-befe-4b6d-8ee3-6278037fdc5f)
