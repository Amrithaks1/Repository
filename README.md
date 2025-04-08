# Faculty Salary Data Analysis

This project performs basic exploratory data analysis (EDA) on a faculty salary dataset. It provides a preview of the dataset, summary statistics, and calculates the average salary by academic rank.

# Project Title
Salary Data Analysis Using Python

# Short Description
This project analyzes faculty salary data using Python to explore relationships between academic rank, experience, and salary trends.

# Getting Started
# Prerequisites
- Python 3.x  
- pandas

# Installing

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/yourusername/faculty-salaries-analysis.git
2. Navigate to the project directory:
    ```bash
    cd faculty-salaries-analysis
3. Launch the notebook:
    ```bash
    jupyter notebook Salaries.ipynb
4. Install the required python packages
   pip install pandas

# Running the Tests
To verify that the script functions correctly, follow these steps:
-  Ensure you have a sample dataset (CSV file) containing salaries data.
-  Modify the script to read from the dataset if necessary.
  - Execute the script using the following command:
     ```sh
     python Salaries.py

# Breakdown of Test
1. Import pandas
    ```bash
    import pandas as pd
* Explanation:
    - This imports the pandas library and gives it the alias pd.
2. Load the dataset
    ```bash
    df = pd.read_csv("Salaries.csv")
* Explanation:
- pd.read_csv("Salaries.csv") reads the Salaries.csv file and loads it into a pandas DataFrame (a table-like structure).
3. Show Basic Info
   ```bash
   print("Dataset Preview:")
   print(df.head())
* Explanation:
  - df.head() displays the first 5 rows of the dataset. This helps you get a quick look at the structure of the data and its contents (e.g., values, column names).
4. Show columns in the dataset
   ```bash
   print("Columns in the dataset:")
   print(df.columns.tolist())
* Explanation:
 - df.columns returns the column names of the DataFrame as an Index object.
 - .tolist() converts the Index object into a regular Python list, which is easier to read and use.

5. Show Summary statistics
    ```bash
    print("\nSummary Statistics:")
    print(df.describe(include='all'))
* Explanation:
  - df.describe(include='all') generates summary statistics of the dataset.
  - When include='all' is added, it also includes stats for non-numeric columns (e.g., categorical variables like rank or sex), such as the most frequent value (top) and its frequency (freq).

6. Check if required columns are present
   ```bash
   if 'rank' in df.columns and 'salary' in df.columns:
    # Clean salary column if needed
    df['salary'] = pd.to_numeric(df['salary'], errors='coerce')
    
    # Average salary by rank
    avg_salary = df.groupby('rank')['salary'].mean().sort_values(ascending=False)
    print("\nAverage Salary by Rank:")
    print(avg_salary)
else:
    print("\nRequired columns ('rank' and 'salary') not found in the dataset.")
    * Explanation:
    - df['salary'] = pd.to_numeric(df['salary'], errors='coerce') attempts to convert the salary column to numeric values (e.g., integers or floats).
    errors='coerce' ensures that any non-numeric values (like strings) in the salary column are replaced with NaN (Not a Number).
    - df.groupby('rank')['salary'].mean() groups the dataset by the rank column and calculates the average salary for each rank.
    - .sort_values(ascending=False) sorts the results in descending order to show the highest average salary first.






