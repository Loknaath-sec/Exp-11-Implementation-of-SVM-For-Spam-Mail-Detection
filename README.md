# Exp-11 Implementation of SVM For Spam Mail D etection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1. Start the Program.

Step 2. Import the necessary packages.

Step 3. Read the given csv file and display the few contents of the data.

Step 4. Assign the features for x and y respectively.

Step 5. Split the x and y sets into train and test sets.

Step 6. Convert the Alphabetical data to numeric using CountVectorizer.

Step 7. Predict the number of spam in the data using SVC (C-Support Vector Classification) method of SVM (Support vector machine) in sklearn library.

Step 8. Find the accuracy of the model.

Step 9. End the Program.

## Program:
```
Program to implement the SVM For Spam Mail Detection
Developed by: Loknaath P
RegisterNumber: 212223240080
```
```python
import chardet
file="spam.csv"
with open(file,'rb') as rawdata:
    result=chardet.detect(rawdata.read(100000))
result

import pandas as pd
data=pd.read_csv("spam.csv",encoding='Windows-1252')

data.head()

data.info()

data.isnull().sum()

x=data["v1"].values
y=data["v2"].values

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()

x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)

from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn import metrics
accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

```

## Output:

### Head Function
![image](https://github.com/user-attachments/assets/7ede2cca-127d-42fc-9243-d13c4446a737)

### Data Information
![image](https://github.com/user-attachments/assets/d4bc7796-2ed8-44ab-a628-9a64488e0c58)

### Y-Predict
![image](https://github.com/user-attachments/assets/dba44c43-6a45-48cc-8cc8-fce359218d70)

### Accuracy
![image](https://github.com/user-attachments/assets/3f080592-62fa-49e8-b5ce-aa17aefd8161)


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
