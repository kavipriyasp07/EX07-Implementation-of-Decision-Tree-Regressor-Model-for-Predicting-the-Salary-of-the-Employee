![Screenshot 2024-10-17 114153](https://github.com/user-attachments/assets/5d3da6b7-c2fb-4ed0-95e6-e2ca854ec9d9)# EX 7 Implementation of Decision Tree Regressor Model for Predicting the Salary of the Employee
## DATE:
## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the Dataset: Import the data (e.g., employee salary data) into a pandas DataFrame.
2. Handle Missing Values: Identify and either fill or remove missing values.
3. Encode Categorical Variables: Convert categorical columns (e.g., department, gender) into
numerical form using label encoding or one-hot encoding.
4. Split the Dataset: Define your features (X) and target (y), then split the data into training and
testing sets.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: kavipria S.P
RegisterNumber:2305002011  
*/
import pandas as pd
data=pd.read_csv("/content/Salary_EX7.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
x.head()
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
mse
r2=metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```

## Output:
![Screenshot 2024-10-17 114057](https://github.com/user-attachments/assets/40dc2968-8497-4402-84ff-58553f58effe)
![Screenshot 2024-10-17 114108](https://github.com/user-attachments/assets/374fd329-1d52-4daa-83d0-307f16480721)
![Screenshot 2024-10-17 114117](https://github.com/user-attachments/assets/5e288570-db31-43b7-948e-22d847c4e626)
![Screenshot 2024-10-17 114124](https://github.com/user-attachments/assets/1183818b-1980-4a76-ae4c-99cd6fa91801)
![Screenshot 2024-10-17 114153](https://github.com/user-attachments/assets/58c2224a-dbda-40c0-aed4-b5eac671a5a2)




## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
