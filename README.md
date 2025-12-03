##First commit loading dataset
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, classification_report, confusion_matrix


df = pd.read_csv("application_record.csv")
credit = pd.read_csv("credit_record.csv")


print("Application record:")
display(df.head())

print("Credit record:")
display(credit.head())


print(df.info())
print(df.describe())


df.isna().sum()


df["dummy_target"] = np.random.randint(0, 2, size=len(df))


X = df.select_dtypes(include=[np.number]).drop(columns=["dummy_target"])
y = df["dummy_target"]

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)


model = DecisionTreeClassifier()
model.fit(X_train, y_train)

preds = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, preds))
print(classification_report(y_test, preds))
print(confusion_matrix(y_test, preds))

print("Baseline model complete —placeholder target used.")
