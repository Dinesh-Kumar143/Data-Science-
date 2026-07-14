# Cleaning and Analyzing Student Data

An exploratory data analysis (EDA) project that cleans a student performance dataset and visualizes relationships between study habits, demographics, and academic outcomes.

## 📁 Project Structure

```
Project 2/
├── Cleaning_and_Analyzing_Student_Data.ipynb   # Main notebook — cleaning & EDA
├── student_data.csv                            # Dataset
└── README.md
```

## 📊 Dataset

`student_data.csv` contains **395 records and 33 columns** describing secondary school students, sourced from Kaggle's [Student Performance Dataset](https://www.kaggle.com/datasets/devansodariya/student-performance-data). It includes demographic details (school, sex, age, address, family background), lifestyle factors (study time, travel time, free time, alcohol consumption, health), and academic performance (`G1`, `G2`, `G3` grades). The dataset has no missing values.

## 🔍 Project Workflow

1. **Understanding the data**
   - Loaded the dataset and displayed all columns for full visibility.
   - Reviewed shape (395 rows × 33 columns), summary statistics, data types, and the number of unique values per column.
2. **Cleaning the data**
   - Dropped columns not needed for the analysis: `famsize`, `Pstatus`, `Medu`, `Fedu`, `Mjob`, `Fjob`, `reason`, `guardian`, `romantic`, `famrel` — reducing the dataset to 395 rows × 23 columns.
3. **Understanding relationships**
   - Built a correlation heatmap across the cleaned features to spot relationships between variables (e.g. study time, absences, failures, grades).
   - Reviewed summary statistics and data types on the cleaned dataset.
4. **Visualization**
   - Pair plot of `studytime`, `failures`, `freetime`, and `absences` to explore pairwise relationships.
   - Box plot of the same features to check for outliers and spread.
   - Histogram of the cleaned dataset's distributions.
   - Relational scatter plot of `traveltime` vs. `studytime`, colored by `sex`, to compare patterns between male and female students.

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** pandas, numpy, seaborn, matplotlib

## 🚀 Getting Started

1. Clone the repository and navigate to the `Project 2` folder.
2. Install the required dependencies:
   ```bash
   pip install pandas numpy seaborn matplotlib
   ```
3. Open and run the notebook:
   ```bash
   jupyter notebook "Cleaning_and_Analyzing_Student_Data.ipynb"
   ```
   > Note: the notebook reads the dataset from a `student Performance Dataset/` subfolder. Adjust the file path if your CSV is in the project root instead.

## 🔮 Possible Improvements

- Turn the correlation and pairplot observations into written insights (e.g. how `failures` and `absences` relate to final grades `G3`).
- Add a predictive model (e.g. regression on `G3`) on top of the current EDA.
- Investigate and, where useful, encode categorical columns (like `sex`, `school`, `address`) for deeper analysis.
