# Ex:05 Feature Generation
# Aim:
To read the given data and perform Feature Generation process and save the data to a file.
# Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
# Algorithm:
Step1: Read the given Data.

Step2: Clean the Data Set using Data Cleaning Process.

Step3: Apply Feature Generation techniques to all the feature of the data set.

Step4: Save the data to the file
# Program:
```
Developed By:THARIKA S
Register No: 212222230159
Encoding.csv:
import pandas as pd
df=pd.read_csv('Encoding Data.csv')
df.head()
df['ord_2'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot']
en= OrdinalEncoder(categories = [climate])
df['ord_2']=en.fit_transform(df[["ord_2"]])
df
le = LabelEncoder()
df['Nom_0'] = le.fit_transform(df[["nom_0"]])
df  
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df = pd.concat([df,data],axis=1)
df
be = BinaryEncoder()
data = be.fit_transform(df['bin_2'])
df = pd.concat([df,data],axis=1)
df
```
# Output:
Initial data:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/8d8972ac-6ddd-49be-8c14-bfb3b5d142b6)
Unique data:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/9f52fcdf-43b9-47ac-8f04-0bc9e753b15c)
Original Encoder:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/3546b81c-3d03-45c6-a127-e079e5881250)
Label Encoder:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/b35457bd-a202-46b9-b5f7-c198292bcc53)
Binary Encoder:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/8dae6ff8-7d2b-487a-99ba-e8d4268aa1d2)
Data.csv:
```
import pandas as pd
df1 = pd.read_csv("data.csv")
df.head()
df['Ord_1'].unique()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
climate = ['Cold','Warm','Hot','Very Hot']
en= OrdinalEncoder(categories = [climate])
df['Ord_1']=en.fit_transform(df[["Ord_1"]])
df.head()
df['Ord_2'].unique()
cl = ['High School','Diploma','Bachelors','Masters','PhD']
en= OrdinalEncoder(categories = [cl])
df['Ord_2']=en.fit_transform(df[["Ord_2"]])
df.head()
le = LabelEncoder()
df['City'] = le.fit_transform(df[["City"]])
df.head()
from category_encoders import BinaryEncoder
be= BinaryEncoder()
data= be.fit_transform(df['bin_1'])
df= pd.concat([df,data],axis=1)
df.head()
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data1 = be.fit_transform(df['bin_2'])
df= pd.concat([df1,data1],axis=1)
df
```
Output:
Initial data:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/ac1538a0-84e4-4d75-a6a5-bd0a65317937)
Unique data:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/b0066e6f-1a06-4751-a804-b7990e7be922)
Original Encoder:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/2ef4204c-9c44-4db5-8be1-a0c5c54c896c)
Label Encoder:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/90d664fc-e45a-46ca-8f5d-a38e207f4706)
Binary Encoder:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/b27bdd7c-a6fa-4b88-80a3-db7bfc040d3c)
BMI.csv:
```
import pandas as pd
df2 = pd.read_csv("/content/bmi.csv")
df2.head()
be = BinaryEncoder()
data2 = be.fit_transform(df2['Gender'])
df2  = pd.concat([df2,data2],axis=1)
df2
df2 = pd.get_dummies(df2, prefix=['Index'] ,columns=['Index'])
df2
```
Output:
Initial data:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/677aab48-b80d-4029-841d-be6926ca5d8e)
Binary Encoder:
![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/7b33bcd7-1126-4bc6-aad8-4c5697b73ca2)
Dummies:![image](https://github.com/tharikasankar/ODD2023-Datascience-Ex-05/assets/119475507/491ea61e-3071-4d08-a17d-36349de40054)

# Result:
The Feature Generation process was performed and saved the data to a file.



