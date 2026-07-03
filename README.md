# Smart Lender Project – Decision Tree Model

## Objective

This module builds and evaluates a Decision Tree classifier for predicting loan approval status.

The model uses preprocessed training and testing data to learn patterns from applicant details such as income, credit history, education, employment status, and loan amount.

---

## Libraries Used

```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
```

---

## Decision Tree Model Code

```python
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Importing and building the Decision Tree model
def decisionTree(X_train, X_test, y_train, y_test):

    # Initialize the model
    model = DecisionTreeClassifier(random_state=42)

    # Train the model
    model.fit(X_train, y_train)

    # Generate predictions
    y_train_pred = model.predict(X_train)
    y_test_pred = model.predict(X_test)

    # Calculate accuracy
    train_accuracy = accuracy_score(y_train, y_train_pred)
    test_accuracy = accuracy_score(y_test, y_test_pred)

    print("Training Accuracy:", train_accuracy)
    print("Testing Accuracy:", test_accuracy)

    # Model evaluation
    print("\nConfusion Matrix:")
    print(confusion_matrix(y_test, y_test_pred))

    print("\nClassification Report:")
    print(classification_report(y_test, y_test_pred))

    return model
```

---

## Function Call

```python
decision_tree_model = decisionTree(X_train, X_test, y_train, y_test)
```

> `X_train`, `X_test`, `y_train`, and `y_test` are created after data preprocessing and train-test splitting.

---

## Model Evaluation

The Decision Tree model is evaluated using:

- **Training accuracy** — performance on the data used to train the model.
- **Testing accuracy** — performance on unseen test data.
- **Confusion matrix** — shows correct and incorrect loan approval predictions.
- **Classification report** — provides precision, recall, F1-score, and support for each class.

---

## Conclusion

The `decisionTree()` function trains a Decision Tree classifier and evaluates its performance for the Smart Lender loan approval prediction system. The trained model can later be compared with Random Forest, KNN, and XGBoost models to select the best-performing model.
