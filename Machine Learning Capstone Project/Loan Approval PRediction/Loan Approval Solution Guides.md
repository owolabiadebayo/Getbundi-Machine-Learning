# Loan Approval Prediction Project

## Overview

This project involves predicting loan approval status for applicants using Python and a machine learning algorithm called Random Forest Classifier. The dataset contains features related to applicants, and the goal is to predict whether a loan application will be approved (1) or not approved (0).

## Steps

### 1. Load the Data

```python
import pandas as pd

# Load the dataset (replace 'dataset.csv' with the actual filename)
data = pd.read_csv('dataset.csv')
```

### 2. Prepare the Data

```python
from sklearn.model_selection import train_test_split

# Split features (X) and target variable (y)
X = data.drop('Target', axis=1)
y = data['Target']

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

### 3. Build and Train the Model

```python
from sklearn.ensemble import RandomForestClassifier

# Create a Random Forest Classifier
classifier = RandomForestClassifier(random_state=42)

# Train the classifier
classifier.fit(X_train, y_train)
```

### 4. Make Predictions

```python
# Make predictions on the test data
predictions = classifier.predict(X_test)
```

### 5. Evaluate the Model

```python
from sklearn.metrics import accuracy_score

# Calculate accuracy
accuracy = accuracy_score(y_test, predictions)
print(f'Accuracy: {accuracy:.2f}')
```

## Conclusion

This simplified project demonstrates the fundamental steps of predicting loan approval status using Python and a Random Forest Classifier. Remember to replace `'dataset.csv'` with your actual dataset filename and customize the code as needed for your specific project.
