# college-set
Exploring college majors, career paths, required skills, and job opportunities to support informed career choices.
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
data = pd.read_csv("college_major_career.csv")

# Display basic information
print("Dataset Preview:")
print(data.head())

print("\nDataset Information:")
print(data.info())

# Check for missing values
print("\nMissing Values:")
print(data.isnull().sum())

# Basic statistics
print("\nStatistical Summary:")
print(data.describe())

# Average salary by major
average_salary = data.groupby("Major")["Median Salary"].mean().sort_values(ascending=False)

print("\nAverage Salary by Major:")
print(average_salary)

# Visualize top 10 majors by salary
average_salary.head(10).plot(kind="bar", figsize=(10, 6))

plt.title("Top 10 College Majors by Median Salary")
plt.xlabel("College Major")
plt.ylabel("Median Salary")
plt.xticks(rotation=45, ha="right")
plt.tight_layout()
plt.show()

# Employment rate by major
employment_rate = data.groupby("Major")["Employment Rate"].mean().sort_values(ascending=False)

print("\nEmployment Rate by Major:")
print(employment_rate)
