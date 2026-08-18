# Pandas-Matplotlib-HR-Analysis
This project analyzes an HR employee dataset using Python. It demonstrates data manipulation with Pandas and NumPy, and data visualization with Matplotlib by exploring employee demographics, department-wise statistics, attrition, marital status, monthly income, and age distribution.
# Python Data Analysis Project – Employee Dataset

## 📌 Project Overview

This project focuses on analyzing an employee dataset using Python.
The objective is to perform basic data analysis and create meaningful
visualizations to understand employee-related information such as
age, department, gender, monthly income, overtime, marital status,
and attrition.

The project was completed as part of a Python Data Analysis project
and examination.

---

## 🎯 Objectives

The main objectives of this project are:

- Load and explore an employee dataset using Pandas.
- Understand the structure of the dataset.
- Perform basic statistical analysis.
- Analyze employees across different departments.
- Calculate average employee age.
- Analyze monthly income across departments.
- Analyze overtime participation.
- Create meaningful data visualizations using Matplotlib and Seaborn.

---

## 🛠️ Technologies Used

- Python
- Pandas
- Matplotlib
- VS Code
- Git & GitHub
## 📊 Dataset

The project uses an employee dataset containing information such as
Age, Department, Gender, Monthly Income, Overtime, Marital Status,
and Attrition.

📁 [Click here to view the raw dataset](https://1drv.ms/x/c/3995AA6664163EE2/IQDgfPG5QfmWT7rKFCS_orxEAbXdZD7pTasI5-6K3EmMXv8?e=jVWrY4)

# Code
# 🔹 Section A – Dataset Basics

## 1. Loading the Dataset

The dataset was imported into a Pandas DataFrame using pd.read_excel().

python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_excel("hrm1.xlsx")
print(df)

![Output](https://raw.githubusercontent.com/SABIHA012/Pandas-Matplotlib-HR-Analysis/d5d863aa305ae1f7b00348caf16203354cddd286/WhatsApp%20Image%202026-08-18%20at%2012.01.20%20PM.jpeg)




---

2. Displaying the First 5 Rows

The head() function was used to display the first five rows of the dataset.

df.head(5)

Output
![output](https://raw.githubusercontent.com/SABIHA012/Pandas-Matplotlib-HR-Analysis/d5d863aa305ae1f7b00348caf16203354cddd286/WhatsApp%20Image%202026-08-18%20at%2012.02.09%20PM.jpeg)



---

3. Displaying Column Names

The columns attribute was used to display all the column names in the dataset.

df.columns

![Output](https://raw.githubusercontent.com/SABIHA012/Pandas-Matplotlib-HR-Analysis/d5d863aa305ae1f7b00348caf16203354cddd286/WhatsApp%20Image%202026-08-18%20at%2012.02.44%20PM.jpeg)




---

4. Checking the Number of Rows and Columns

The shape attribute was used to find the total number of rows and columns.

df.shape

Output

(1470, 35)


---

🔹 Section B – Data Analysis

5. Average Age of Employees

The average age of employees was calculated using the mean() function.

a = df['Age'].mean()

print(f'AVERAGE AGE OF EMPLOYEES: {a:.2f}')

Output

AVERAGE AGE OF EMPLOYEES: 36.92


---

6. Number of Employees in Each Department

The number of employees in each department was calculated using groupby() and count().

c = df.groupby('Department')['EmployeeNumber'].count()

print('NUMBER OF EMPLOYEES IN EACH DEPARTMENT:', c)

Output

Human Resources                 63
Research & Development         961
Sales                          446


---

7. Average Monthly Income for Each Department

The average monthly income of employees was calculated department-wise.

m = df.groupby('Department')['MonthlyIncome'].mean()

print('MONTHLY INCOME DEPARTMENTWISE:', m)

Output

Human Resources                 6654.507937
Research & Development           6281.252862
Sales                            6591.172646


---

8. Number of Employees Working Overtime

The number of employees working overtime was calculated using the OverTime column.

o = df[df['OverTime'] == 'YES'].count()

print('NUMBER OF PEOPLE DOING OVERTIME:', o)

Output

NUMBER OF PEOPLE DOING OVERTIME: 1470


---

🔹 Section C – Data Visualization

9. Number of Employees in Each Department

A bar chart was created to show the number of employees in each department.

re = df.groupby('Department')['EmployeeCount'].count()

bars = plt.bar(re.index, re.values)

plt.bar_label(bars)

plt.xlabel('Department')
plt.ylabel('Number of employees')
plt.title('NUMBER OF EMPLOYEES DEPARTMENTWISE')

plt.show()

![Output]()




---

10. Number of Employees by Gender

A bar chart was created to show the distribution of employees by gender.

re1 = df.groupby('Gender')['EmployeeCount'].count()

bars = plt.bar(re1.index, re1.values)

plt.bar_label(bars)

plt.xlabel('Gender')
plt.ylabel('Number of employees')
plt.title('NUMBER OF EMPLOYEES GENDERWISE')

plt.show()

![Output](https://raw.githubusercontent.com/SABIHA012/Pandas-Matplotlib-HR-Analysis/d5d863aa305ae1f7b00348caf16203354cddd286/WhatsApp%20Image%202026-08-18%20at%2012.02.46%20PM.jpeg)




---

11. Marital Status Distribution

A pie chart was created to show the distribution of employees according to marital status.

re2 = df.groupby('MaritalStatus')['EmployeeCount'].count()

plt.figure(figsize=(6,6))

plt.pie(
    re2.values,
    labels=re2.index,
    autopct='%1.1f%%',
    startangle=90
)

plt.title('Marital status distribution')

plt.show()

![Output](https://raw.githubusercontent.com/SABIHA012/Pandas-Matplotlib-HR-Analysis/d5d863aa305ae1f7b00348caf16203354cddd286/WhatsApp%20Image%202026-08-18%20at%2012.02.54%20PM.jpeg)




---

12. Age Distribution

A histogram was created to visualize the age distribution of employees.

plt.figure(figsize=(7,5))

plt.hist(
    df['Age'],
    bins=10,
    edgecolor='black'
)

plt.xlabel('Age')
plt.ylabel('Number of Employees')
plt.title('AGE DISTRIBUTION')

plt.show()

![Output](https://raw.githubusercontent.com/SABIHA012/Pandas-Matplotlib-HR-Analysis/d5d863aa305ae1f7b00348caf16203354cddd286/WhatsApp%20Image%202026-08-18%20at%2012.02.50%20PM.jpeg)




---

13. Employee Attrition

A bar chart was created to compare employee attrition.

re3 = df.groupby('Attrition')['EmployeeCount'].count()

bars = plt.bar(re3.index, re3.values)

plt.bar_label(bars)

plt.xlabel('Attrition')
plt.ylabel('Number of Employees')
plt.title('ATTRITION (YES/NO)')

plt.show()

![output]()




---

14. Average Monthly Income by Gender

A bar chart was created to compare the average monthly income of male and female employees.

re4 = df.groupby('Gender')['MonthlyIncome'].mean()

bars = plt.bar(re4.index, re4.values)

plt.bar_label(bars, fmt='%.2f')

plt.xlabel('Gender')
plt.ylabel('Average Monthly Income')
plt.title('AVERAGE MONTHLY INCOME BY GENDER')

plt.show()



![Output](https://raw.githubusercontent.com/SABIHA012/Pandas-Matplotlib-HR-Analysis/d5d863aa305ae1f7b00348caf16203354cddd286/WhatsApp%20Image%202026-08-18%20at%2012.02.56%20PM.jpeg)


---

📈 Project Summary

This project demonstrates the use of Python for basic employee data analysis and visualization.

The analysis includes:

Loading and exploring datasets using Pandas

Finding statistical values such as average age

Grouping employees by department and gender

Analyzing monthly income

Studying employee attrition

Understanding marital status distribution

Visualizing age distribution

Creating bar charts, pie charts, and histograms using Matplotlib



---

📁 Project Files

File	Description

README.md	Project documentation
employee_data_analysis.ipynb	Python code and analysis
hrm1.xlsx	Raw dataset used for analysis
screenshots/	Output visualizations



---

👩‍💻 Author

Sabiha Mehar

BBA Business Analytics
