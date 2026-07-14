# Predicting Canada's Per Capita Income (Linear Regression)

A simple machine learning project that builds a **Linear Regression model** to predict Canada's per capita income (in US$) based on historical yearly data, and uses it to forecast income for future years.

## 📁 Project Structure

```
ML_Linear Regression_Project/
├── Predicting_Canada's_per_capita_income_ML_Model.ipynb   # Main notebook — model building & analysis
├── canada_per_capita_income.csv                           # Dataset (year vs. per capita income)
├── Predicted_values.csv                                   # Model predictions on the test set
└── README.md
```

## 📊 Dataset

`canada_per_capita_income.csv` contains two columns:

| Column | Description |
|---|---|
| `year` | Calendar year (1970–2016) |
| `per capita income (US$)` | Canada's per capita income for that year, in US dollars |

The dataset has no missing values.

## 🔍 Project Workflow

1. **Import libraries** — pandas, matplotlib, and scikit-learn.
2. **Load and inspect the data** — read the CSV and check for null values.
3. **Feature/target selection** — `year` is used as the input feature (`X`) and `per capita income (US$)` as the target (`Y`).
4. **Train/test split** — data split 70/30 into training and test sets.
5. **Model training** — fit a `LinearRegression` model on the training data.
6. **Model inspection** — extract the fitted line's intercept and coefficient (slope) to understand the trend:
   - Intercept (b): **-1,618,581.22**
   - Coefficient (m): **821.45**

   i.e. the model follows `income = 821.45 × year − 1,618,581.22`
7. **Prediction & evaluation**
   - Predicted income for **2030**: **≈ $48,953**
   - Predicted income for **2020**: **≈ $40,739**
   - Generated predictions for the test set and saved them to `Predicted_values.csv`.
8. **Visualization** — plotted the actual data points against the model's predicted values to visually assess the fit.

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** pandas, matplotlib, scikit-learn

## 🚀 Getting Started

1. Clone the repository and navigate to the `ML_Linear Regression_Project` folder.
2. Install the required dependencies:
   ```bash
   pip install pandas matplotlib scikit-learn
   ```
3. Open and run the notebook:
   ```bash
   jupyter notebook "Predicting_Canada's_per_capita_income_ML_Model.ipynb"
   ```
   > Note: the notebook reads the dataset from a `Task/` subfolder (`Task/canada_per_capita_income.csv`). Adjust the file path if your CSV is in the project root instead.

## 📈 Results

The model captures a clear, strong upward linear trend in Canada's per capita income from 1970 onward, and extrapolates that trend to estimate income in future years (e.g. 2020 and 2030). The scatter plot of actual vs. predicted values shows the fitted line tracking the overall trend closely, though a simple linear model can't capture short-term fluctuations or economic shocks.

## 🔮 Possible Improvements

- Evaluate the model quantitatively (e.g. R² score, MAE/RMSE) rather than relying on visual inspection alone.
- Try polynomial regression to capture potential non-linear trends in the data.
- Use cross-validation for a more robust estimate of model performance given the small dataset size.
