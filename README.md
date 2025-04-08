# 🚢 Titanic Dataset - Exploratory Data Analysis (EDA)

## 📌 Objective
The objective of this project is to explore and analyze the Titanic dataset using various data analysis techniques. The main goals include:
- Loading and cleaning the dataset
- Handling missing values and formatting issues
- Performing univariate and bivariate analysis
- Visualizing trends related to passenger survival
- Drawing key insights from the data

---

## 🛠 Tools & Technologies
- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
  
--

## ✅ Requirements  
- Load the dataset  
- Clean the dataset (handle null values, drop irrelevant columns, correct datatypes)  
- Perform Univariate Analysis  
- Perform Bivariate Analysis  
- Visualize survival trends  
- Provide key insights and observations
  
---

## 📁 Code Walkthrough

```python
# Importing Required Libraries
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load Dataset
df = pd.read_excel("titanic3.xls")

# Initial Cleaning
df.drop(columns=['name', 'ticket', 'cabin', 'boat', 'body', 'home.dest'], inplace=True)
df['age'].fillna(df['age'].median(), inplace=True)
df['embarked'].fillna(df['embarked'].mode()[0], inplace=True)
df.dropna(subset=['fare'], inplace=True)
df['age'] = df['age'].astype(int)

# Univariate Analysis
plt.figure(figsize=(6, 4))
ax = sns.countplot(x='sex', data=df, palette='pastel')
plt.title('Passenger Count by Sex')
for p in ax.patches:
    ax.annotate(f'{p.get_height()}', (p.get_x() + p.get_width()/2., p.get_height()),
                ha='center', va='baseline', fontsize=11, color='black', xytext=(0, 5),
                textcoords='offset points')
plt.show()

# Survival Count
plt.figure(figsize=(6, 4))
ax = sns.countplot(x='survived', data=df, palette='viridis')
plt.title("Survival Counts (0 = Did Not Survive, 1 = Survived)")
for p in ax.patches:
    ax.annotate(f'{p.get_height()}', (p.get_x() + p.get_width() / 2., p.get_height()), 
                ha='center', va='bottom')
plt.xlabel("Survived")
plt.ylabel("Count")
plt.show()

# Bivariate Analysis - Survival by Sex
sns.countplot(x='sex', hue='survived', data=df, palette='Set2')
plt.title('Survival by Gender')
plt.show()

# Bivariate Analysis - Survival by Class
sns.countplot(x='pclass', hue='survived', data=df, palette='Set1')
plt.title('Survival by Passenger Class')
plt.show()

## 🧠 Insights & Observations  
- **Female passengers** had a significantly higher survival rate  
- **1st class passengers** were more likely to survive  
- **Younger passengers (children)** had better chances of survival  
- Passengers who **embarked from Cherbourg (C)** had higher survival rate  

---

## 🌐 Scope  
- Practicing data cleaning and analysis on a real-world dataset  
- Strengthening Python and visualization skills  
- Building storytelling ability through data-driven insights  
- Laying foundation for future projects and interviews  

---

## ✅ Conclusion  
- Dataset was cleaned and preprocessed successfully  
- Univariate and Bivariate analysis revealed important trends  
- Key patterns in survival were visualized using plots  
- The project demonstrates foundational data analysis skills  

---

## 🙏 Thank You  
If you found this project insightful, feel free to star the repository ⭐ or connect with me on [LinkedIn](https://www.linkedin.com/in/your-profile)!

---
