# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas library to read csv or excel file.
2. Import LabelEncoder using sklearn.preprocessing library.
3. Transform the data's using LabelEncoder.
4. Import decision tree classifier from sklearn.tree library to predict the values.
5. Find accuracy.
6. Predict the values.
7. End of the program

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by:NARMATHA K
RegisterNumber:212219040088  
*/
```
~~~
import pandas as pd
data=pd.read_csv("Employee.csv")
data.head()
data.info()
data.isnull().sum()
data["left"].value_counts()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics 
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
dt.predict([[0.5,0.8,9,260,6,0,1,2]])
~~~

## Output:
# HEAD:
![1](https://user-images.githubusercontent.com/95342910/173554779-12ce285a-2341-4f0d-a31a-51f5bba6d16e.png)

# INFO:
![2](https://user-images.githubusercontent.com/95342910/173554889-3cbff384-1ecd-4272-84a6-1001c03d2fd7.png)

# ISNULL:
![3](https://user-images.githubusercontent.com/95342910/173554923-1bd9c081-0be1-4a6b-bfa6-48a11ae15440.png)

# LEFT:
![4](https://user-images.githubusercontent.com/95342910/173554965-46c51246-0278-4c29-b3dc-7effef6b1791.png)

# HEAD USING LABELENCODER:
![5](https://user-images.githubusercontent.com/95342910/173555020-f755baf5-8c49-4ba9-a69d-5bc48e7951ad.png)

# ACCURACY:
![6](https://user-images.githubusercontent.com/95342910/173555067-ce8f2275-252a-472a-abc5-1c80b237fb5b.png)

# PREDICT:
![7](https://user-images.githubusercontent.com/95342910/173555097-211ffa9b-41fc-4ee1-b3a5-cc2a99806b10.png)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
