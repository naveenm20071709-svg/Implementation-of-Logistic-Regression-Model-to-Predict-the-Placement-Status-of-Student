# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student

## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
 1.Load and preprocess the dataset (remove unwanted columns and convert categorical data).

2.Split the data into training and testing sets.

3.Train the Logistic Regression model using the training data.

4.Evaluate accuracy and visualize results using a sigmoid curve plot.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: naveen M
RegisterNumber:  212225230198

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression

# Load dataset
data = pd.read_csv("Placement_Data (1).csv")

# Drop salary column (contains missing values)
data = data.drop("salary", axis=1)

# Convert categorical data to numeric
data = pd.get_dummies(data, drop_first=True)

# Features and target
X = data.drop("status_Placed", axis=1)
y = data["status_Placed"]

# Split dataset
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train model
model = LogisticRegression(max_iter=1000)
model.fit(X_train, y_train)

# Accuracy
print("Accuracy:", model.score(X_test, y_test))


# -------------------------------
# 📈 Logistic Regression Plot
# -------------------------------

# Use only ONE feature for plotting
X1 = X.iloc[:, 0].values.reshape(-1, 1)

# Train model on single feature
model_plot = LogisticRegression(max_iter=1000)
model_plot.fit(X1, y)

# Scatter plot
plt.scatter(X1, y, color='blue')

# Sigmoid curve
x_values = np.linspace(X1.min(), X1.max(), 100)
y_values = model_plot.predict_proba(x_values.reshape(-1,1))[:,1]

plt.plot(x_values, y_values)

plt.xlabel("Feature")
plt.ylabel("Probability")
plt.title("Logistic Regression Curve")
plt.show()
*/
```

## Output:
<img width="810" height="612" alt="Screenshot 2026-05-13 105939" src="https://github.com/user-attachments/assets/5d3c7bd0-1ebf-44e5-b2c0-d26af2976ed6" />



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
