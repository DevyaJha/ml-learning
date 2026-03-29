# 🚀 ML Learning Journey — Notes

---

## 🧠 1. Python Basics

### Variables

```python
name = "Divya"
age = 31
```

---

### Printing

#### f-string (Recommended ⭐)

```python
print(f"My name is {name} and I am {age} years old")
```

---

## 🔁 2. Lists

### Create list

```python
items = ["milk", "toys"]
```

### Add item

```python
items.append("diapers")
```

### Loop

```python
for item in items:
    print(item)
```

---

## 📦 3. Dictionaries

### Create dictionary

```python
person = {
    "name": "Divya",
    "age": 31
}
```

### Access

```python
person["name"]
```

### Add new key

```python
person["city"] = "Delhi"
```

### Loop

```python
for key, value in person.items():
    print(f"{key}: {value}")
```

---

## 📊 4. Pandas Basics

```python
import pandas as pd
```

### Create DataFrame

```python
df = pd.DataFrame({
    "name": ["Kuhu", "Baby2"],
    "age": [5.5, 6]
})
```

### View data

```python
df.head()
```

### Access column

```python
df["age"]
```

### Filter data

```python
df[df["age"] > 5]
```

### Add column

```python
df["age_next_month"] = df["age"] + 1
```

### Aggregation

```python
df["age"].mean()
df["weight"].max()
```

---

## 📁 5. CSV Handling

### Save CSV

```python
df.to_csv("file.csv", index=False)
```

### Read CSV

```python
df = pd.read_csv("file.csv")
```

---

## 🧹 6. Data Cleaning

### Check missing values

```python
df.isnull().sum()
```

### Fill missing values

```python
df["age"] = df["age"].fillna(df["age"].mean())
df["name"] = df["name"].fillna("Unknown")
```

---

### Sample code

```
import pandas as pd
data = {
    "name": ["Kuhu", "Baby2", None],
    "age": [5.5, None, 7],
    "weight": [7.2, 7.5, 8.0]
}

df = pd.DataFrame(data)
df["age"] = df["age"].fillna(0)
df["age_next_month"] = df["age"] + 1
df["name"] = df["name"].fillna("Unknown")

print(df)
df.to_csv("baby_data.csv", index=False)
```

Output - 
<img width="385" height="92" alt="image" src="https://github.com/user-attachments/assets/f6268c76-f60a-467f-977a-377f0856fd43" />


## 🧠 Key Learnings

* Use **f-strings** for printing
* Use **Pandas instead of loops** for data
* Data is usually **messy (NaN values)**
* Cleaning data is required before ML

---

## 🚀 ML Workflow

```
Data → Pandas → Cleaning → Analysis → Model (next step)
```

---

