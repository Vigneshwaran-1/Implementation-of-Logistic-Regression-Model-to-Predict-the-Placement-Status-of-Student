# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student
## Developed by: Vigneshwaran .P
## Register Number: 212224040358
## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm


1. **Start**
2. Load the student data with CGPA, Aptitude Score, and Placement Status.
3. Split the data into training and testing sets.
4. Train the Logistic Regression model and predict placement status.
5. Display the predicted result and model accuracy.

## Program:


## Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
 
```
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score, confusion_matrix


data = {
    'CGPA': [6.5, 7.0, 7.5, 8.0, 8.5, 9.0, 6.0, 7.2, 8.2, 9.2],
    'Aptitude': [50, 55, 60, 65, 70, 80, 45, 58, 68, 85],
    'Placement': [0, 0, 1, 1, 1, 1, 0, 0, 1, 1]
}

df = pd.DataFrame(data)

X = df[['CGPA', 'Aptitude']]
y = df['Placement']

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

model = LogisticRegression()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)

accuracy = accuracy_score(y_test, y_pred)

print("Actual Values:", list(y_test))
print("Predicted Values:", list(y_pred))
print("Accuracy:", accuracy * 100, "%")

# Predict placement for a new student
cgpa = float(input("Enter CGPA: "))
aptitude = float(input("Enter Aptitude Score: "))

prediction = model.predict([[cgpa, aptitude]])

if prediction[0] == 1:
    print("Placement Status: Placed")
else:
    print("Placement Status: Not Placed")
```
## Output:

<img width="833" height="129" alt="image" src="https://github.com/user-attachments/assets/a495386b-056d-4094-bb28-efb9e5d236c2" />


## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
