# Academic Salaries Data Analysis

A Python-based exploratory data analysis (EDA) project focused on understanding faculty salary trends using the `Salaries.csv` dataset. The analysis includes data wrangling, statistical summaries, and visual insights to uncover patterns in compensation across academic roles.

---

## Getting Started

### Prerequisites

To run this project, make sure you have:

- Python 3.x
- Jupyter Notebook or JupyterLab
- The following Python libraries:

```bash
pip install pandas matplotlib seaborn
```

### Installing

1. Clone or download this repository.
2. Ensure `Salaries.csv` is located in the same directory as the notebook.
3. Launch Jupyter Notebook:

```bash
jupyter notebook
```

4. Open and run `Salaries.ipynb`.

---

## Running the Tests

This notebook does not contain unit tests but includes multiple analytical steps:

### Breakdown of Tests

- **Initial Data Inspection**: Checking data structure and previewing rows.
- **Data Cleaning**: Handling missing values and correcting types (if required).
- **Descriptive Statistics**: Summary of salary ranges and distributions.
- **Visual Analysis**:
  - Salary distributions by rank and gender
  - Boxplots and histograms for comparative analysis
  - Correlations (if applicable)

---
## Explanation of Steps:
1. **Import pandas**
   ```bash
   import pandas as pd
**Explanation**:
- This imports the pandas library and gives it the alias pd.
  
2. **Load the datset**
   ```bash
   df = pd.read_csv("Salaries.csv")
**Explanation**:
- pd.read_csv("Salaries.csv") reads the Salaries.csv file and loads it into a pandas DataFrame (a table-like structure).
  
3. **Show basic info**
   ```bash
   print("Dataset Preview:")
   print(df.head())
**Explanation**:
- df.head() displays the first 5 rows of the dataset. This helps you get a quick look at the structure of the data and its contents (e.g., values, column names).
  
4. **Show columns in dataset**
   ```bash
   print("Columns in the dataset:")
   print(df.columns.tolist())
**Explanation**:
- df.columns returns the column names of the DataFrame as an Index object.
- .tolist() converts the Index object into a regular Python list, which is easier to read and use.
  
5. **Show summary statistics**
   ```bash
   print("\nSummary Statistics:")
   print(df.describe(include='all'))
**Explanation**:
- df.describe(include='all') generates summary statistics of the dataset.
- By default, describe() provides statistics for numerical columns (e.g., count, mean, min, max, etc.).
- When include='all' is added, it also includes stats for non-numeric columns (e.g., categorical variables like rank or sex), such as the most frequent value (top) and its frequency (freq).
- 
6. **Check if required columns are present**
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
  
**Explanation**:
- df['salary'] = pd.to_numeric(df['salary'], errors='coerce') attempts to convert the salary column to numeric values (e.g., integers or floats).
- df.groupby('rank')['salary'].mean() groups the dataset by the rank column and calculates the average salary for each rank.
- .sort_values(ascending=False) sorts the results in descending order to show the highest average salary first.


---

## Deployment

This is a standalone Jupyter Notebook intended for educational or analytical use. No deployment setup is needed.

---

## Author

**AMRITHA KOZHIPARAMBIL SURENDRAN**

---

## License

This project is licensed under the MIT License. You are free to use and modify it with proper credit.

---

## Acknowledgement

- Dataset Source: `Salaries.csv` (typically derived from academic or open salary datasets)
- pandas and matplotlib for analysis and visualization
- Jupyter Project for interactive development
