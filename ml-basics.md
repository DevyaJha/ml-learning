# 🤖 ML Basics — Model Training & Evaluation

---

## 🧠 1. What is Machine Learning?

Machine Learning =
👉 Learning patterns from data to make predictions

Example:

```text
Input (age) → Output (weight)
```

---

## ⚙️ 2. Linear Regression Model

```python
from sklearn.linear_model import LinearRegression
```

👉 Linear Regression

* Finds relationship between input and output
* Example: age ↑ → weight ↑

---

## 📊 3. Preparing Data

```python
X = df[["age"]]   # Input (must be 2D)
y = df["weight"]  # Output
```

---

## ✂️ 4. Train-Test Split

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
```

### 🔍 Explanation

* `test_size=0.2` → 20% data for testing
* `random_state=42` → ensures same split every time

---

### 🧠 Why split?

```text
Train → learn  
Test → evaluate
```

👉 Prevents model from memorizing data

---

## 🏋️ 5. Train Model

```python
model = LinearRegression()
model.fit(X_train, y_train)
```

👉 Model learns pattern from training data

---

## 🔮 6. Make Predictions

```python
y_pred = model.predict(X_test)
```

---

## 📊 7. Compare Results

```python
print("Actual:", list(y_test))
print("Predicted:", y_pred)
```

👉 Check how close predictions are

---

## ⚠️ 8. Feature Name Warning

If you see warning:

```text
X does not have valid feature names
```

👉 Fix by using DataFrame:

```python
new_data = pd.DataFrame({"age": [6.5]})
model.predict(new_data)
```

---

## 🧠 Key Concepts

* `X` → input features
* `y` → output/target
* `fit()` → training
* `predict()` → prediction
* Train/Test split → evaluation

---

## 🔄 ML Workflow (So far)

```text
Data → Pandas → Clean → Split → Train → Predict
```

---

## Sample code

```
import pandas as pd
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split

# Data
data = {
    "age": [5.5, 6, 6.5, 7, 7.5, 8],
    "weight": [7.2, 7.5, 7.7, 8.0, 8.3, 8.5]
}

df = pd.DataFrame(data)

# Input (X) and Output (y)
X = df[["age"]]     # input must be 2D
y = df["weight"]

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# Create model
model = LinearRegression()

# Train model
model.fit(X_train, y_train)

# Predict
# new_data = pd.DataFrame({
#     "age": [6.5]
# })

# predicted_weight = model.predict(new_data)
# predicted_weight = model.predict([[6.5]])

y_pred = model.predict(X_test)
print(X_test)
print(X_train)
print(y_pred)
print("Actual:", list(y_test))
print("Predicted:", y_pred)

# print(f"Predicted weight for age 6.5 is {predicted_weight[0]}")
```
