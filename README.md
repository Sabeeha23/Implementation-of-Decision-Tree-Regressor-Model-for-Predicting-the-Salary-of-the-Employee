# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load the dataset Salary.csv using pandas and view the first few rows.

2.Check dataset information and identify any missing values.

3.Encode the categorical column "Position" into numerical values using LabelEncoder.

4.Define feature variables x as "Position" and "Level", and target variable y as "Salary".

5.Split the dataset into training and testing sets using an 80-20 split.

6.Create a DecisionTreeRegressor model instance.

7.Train the model using the training data.

8.Predict the salary values using the test data.

9.Evaluate the model using Mean Squared Error (MSE) and R² Score.

10.Use the trained model to predict salary for a new input [5, 6].
## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Sabeeha Shaik
Register Number:  212223230176
*/
```

```
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
```
![image](https://github.com/user-attachments/assets/18f59be4-72d5-40ef-b741-b9f9387e2a42)

```
data.info()
```
![image](https://github.com/user-attachments/assets/0b72af3c-87b2-4fcc-bdde-ae9752688e5c)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/5cd8cfd5-b524-423a-9184-06a4a94d7b7f)
```
from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![image](https://github.com/user-attachments/assets/add83b80-dda5-47b5-8924-a2cce764ef89)
```
x=data[["Position","Level"]]
x.head()
```
![image](https://github.com/user-attachments/assets/94d401fa-c4bd-4db2-8305-779e46056581)
```
y=data[["Salary"]]
```
```
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)
```
```
from sklearn.tree import DecisionTreeRegressor
dt = DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_predict = dt.predict(x_test)
```
```
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_predict)
mse
```
![image](https://github.com/user-attachments/assets/7a8f822a-b392-466a-92c5-f5ef464c4dd9)
```
r2 = metrics.r2_score(y_test,y_predict)
r2
```
![image](https://github.com/user-attachments/assets/ccb6f091-2814-4531-9366-18133a4d8e15)
```
dt.predict([[5,6]])
print("Sabeeha Shaik")
print(212223230176)
```
![image](https://github.com/user-attachments/assets/8b234163-e2bd-4c84-a798-4923a2ea5379)


## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
