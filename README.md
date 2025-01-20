# README: Step-by-Step Explanation of `apple_dataset_analysis.ipynb`

## Introduction
This README provides a detailed explanation of each code block in the `apple_dataset_analysis.ipynb` file, which contains data about sales of iphone phones. It serves as a guide for understanding the analysis process and replicating the steps.

---

## Step-by-Step Explanation

### 1. Importing Libraries
```python
import pandas as pd
import seaborn as sns
```
- Imports essential libraries for data manipulation and visualization:
  - `pandas` for handling tabular data.
  - `seaborn` for creating visualizations.

---

### 2. Loading the Dataset
```python
df = pd.read_csv('apple.csv')
```
- Reads the `apple.csv` file into a pandas DataFrame.

---

### 3. Understanding the Dataset
```python
data.info()
```
- Provides a summary of the dataset, including data types and missing values.

---

### 4. Displaying the Column Names
```python
df.columns
```
- Displays all the field names that we are going to work with in the dataset.

---

### 5. Top 5 star rating apple phones
```python
top_5_star_ratings = df.nlargest(5, 'Star Rating')[['Product Name', 'Star Rating']]
top_5_star_ratings
```

---

### 6. Lowest 5 star rating apple phones
```python
lowest_5_star_ratings = df.nsmallest(5, 'Star Rating')[['Product Name', 'Star Rating']]
lowest_5_star_ratings
```

---

### 7. Ratings provided to top 5 star rating apple phones
```python
ratings_top_5 = df.nlargest(5, 'Star Rating')[['Product Name', 'Star Rating', 'Number Of Ratings']]
ratings_top_5
```

---

### 8. Ratings provided to lowest 5 star rating apple phones
```python
ratings_lowest_5 = df.nsmallest(5, 'Star Rating')[['Product Name', 'Star Rating', 'Number Of Ratings']]
ratings_lowest_5
```

---

### 9. Apple phones that have highest number of reviews
```python
highest_reviews_phone = df[df["Number Of Reviews"] == df["Number Of Reviews"].max()]["Product Name"]
highest_reviews_phone
```

---

### 10. Apple phones that have lowest number of reviews
```python
lowest_reviews_phone = df[df["Number Of Reviews"] == df["Number Of Reviews"].min()]["Product Name"]
lowest_reviews_phone
```

---

### 11. Relationship between sale price and number of ratings
```python
relation_price_ratings = df[['Sale Price', 'Number Of Ratings']].corr()
sns.heatmap(relation_price_ratings, annot = True, cmap = "coolwarm")
relation_price_ratings
```

---

### 12. Relationship between sale price and number of reviews
```python
relation_price_reviews = df[['Sale Price', 'Number Of Reviews']].corr()
sns.heatmap(relation_price_reviews, annot = True, cmap = "coolwarm")
relation_price_reviews
```

---

### 13. Relationship between discount percentage and number of reviews
```python
relation_discount_reviews = df[['Discount Percentage', 'Number Of Reviews']].corr()
sns.heatmap(relation_discount_reviews, annot = True, cmap = "coolwarm")
relation_discount_reviews
```

---

### 14. Most expensive apple phone
```python
most_expensive_phone = df[df["Mrp"] == df["Mrp"].max()]["Product Name"]
most_expensive_phone
```

---

### 15. Least expensive apple phone
```python
least_expensive_phone = df[df["Mrp"] == df["Mrp"].min()]["Product Name"]
least_expensive_phone
```

---

## Conclusion
This step-by-step breakdown provides clarity on the purpose and functionality of each code block in the `apple_dataset_analysis.ipynb` file. Follow these explanations to reproduce the analysis and adapt it for similar datasets.
