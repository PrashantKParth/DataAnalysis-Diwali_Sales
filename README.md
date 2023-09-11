# Analyzing The Diwali Sale Data

## Introduction
This repository contains Python code for analyzing Diwali sale data using the Pandas, NumPy, Matplotlib, and Seaborn libraries. The dataset used in this analysis is named "Diwali Sales Data.csv."

## Getting Started
Before running the code, make sure you have the required Python libraries installed. You can install them using pip if you haven't already:

```bash
pip install pandas numpy matplotlib seaborn
```

## Code Overview
The analysis is divided into several sections, each addressing different aspects of the dataset.

### Importing the Data
We start by importing the dataset using Pandas and display a summary of the data.

```python
import pandas as pd

# Import CSV file in Jupyter
data = pd.read_csv(r'C:\Users\prash\OneDrive\Desktop\Diwali Sales Data.csv', encoding='latin-1')

# Display basic information about the data
data.info()
```

### Data Cleaning
We clean the data by dropping unnecessary columns and removing rows with missing values.

```python
# Deleting unwanted columns
delete_columns = ['unnamed1', 'Status']
data1 = data.drop(delete_columns, axis=1)

# Removing rows with missing values
data1.dropna(inplace=True)

# Changing data type of the 'Amount' column
data1['Amount'] = data1['Amount'].astype('int')
```

### Exploratory Data Analysis (EDA)
We perform EDA to gain insights into the data by visualizing various aspects, such as gender distribution, age groups, states, marital status, occupation, and product categories.

```python
# EDA visualizations (sample code provided for each analysis)

# Gender distribution
sns.countplot(x='Gender', data=data1)

# Age group distribution
sns.countplot(x='Age Group', data=data1, hue='Gender')

# State-wise analysis
sns.barplot(x='State', y='Orders', data=sales_state)
sns.barplot(x='State', y='Amount', data=sales_state_amount)

# Marital status analysis
sns.countplot(x='Marital_Status', data=data1)
sns.barplot(x='Marital_Status', y='Amount', data=sales_marital_gender, hue='Gender')

# Occupation analysis
sns.countplot(x='Occupation', data=data1)
sns.barplot(x='Occupation', y='Amount', data=occupation_amount)

# Product category analysis
sns.countplot(x='Product_Category', data=data1)
sns.barplot(x='Product_Category', y='Amount', data=product_cate_amount)

# Most sold products
sns.barplot(x='Product_ID', y='Orders', data=productid_order)
```

## Conclusion
Based on the analysis, we can draw conclusions about the demographics and preferences of Diwali sale customers. The code provides insights into gender distribution, age groups, popular states, marital status, occupation, and preferred product categories. This information can be valuable for marketing and sales strategies during Diwali sales campaigns.
