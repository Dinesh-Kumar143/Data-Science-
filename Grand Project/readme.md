
# Credit Risk Assessment for Loan Approval

A machine learning project that predicts whether a loan applicant is likely to default, using historical credit and demographic data. The goal is to help a lender flag high-risk applications before approval.

## 📁 Project Structure

```
Grand Project/
├── Project Credit Risk Assessment for Loan Approval.ipynb   # Main analysis & modeling notebook
├── credit_risk.csv                                          # Dataset
├── Grand Project.pdf                                         # Project write-up / report
└── readme.md
```

## 📊 Dataset

The dataset (`credit_risk.csv`) contains **32,581 records** and **12 columns** describing loan applicants:

| Column | Description |
|---|---|
| `Id` | Unique applicant identifier |
| `Age` | Applicant's age |
| `Income` | Annual income |
| `Home` | Home ownership status (RENT, OWN, MORTGAGE, OTHER) |
| `Emp_length` | Employment length (years) |
| `Intent` | Purpose of the loan (PERSONAL, EDUCATION, MEDICAL, VENTURE, HOMEIMPROVEMENT, DEBTCONSOLIDATION) |
| `Amount` | Loan amount requested |
| `Rate` | Interest rate |
| `Status` | Target variable — loan status (0 = non-default, 1 = default) |
| `Percent_income` | Loan amount as a percentage of income |
| `Default` | Historical default flag (Y/N) |
| `Cred_length` | Length of credit history (years) |

## 🔍 Project Workflow

1. **Data Loading & Inspection** — loaded the dataset and reviewed structure, data types, and summary statistics.
2. **Data Cleaning**
   - Handled missing values in `Emp_length` (filled with median) and `Rate` (filled with mean).
   - Dropped the non-predictive `Id` column.
   - Removed duplicate rows.
3. **Exploratory Data Analysis (EDA)**
   - Visualized the distribution of loan `Status`, `Home` ownership, `Intent`, and `Default` using count plots.
   - Plotted feature histograms and a correlation heatmap to understand relationships between variables.
4. **Feature Encoding** — converted categorical columns (`Home`, `Intent`, `Default`) into numeric form using `LabelEncoder`.
5. **Train/Test Split** — split the data into training and test sets for model evaluation.
6. **Model Building** — trained and compared multiple classification algorithms:
   - Gaussian Naive Bayes
   - Bernoulli Naive Bayes
   - K-Nearest Neighbors
   - Logistic Regression
   - Decision Tree Classifier
   - Random Forest Classifier
7. **Model Evaluation** — compared training accuracy across models, then evaluated the best-performing model (Random Forest) on the held-out test set using accuracy and a confusion matrix.

## 📈 Results

Training accuracy across models:

| Model | Accuracy |
|---|---|
| Gaussian Naive Bayes | 0.815 |
| Bernoulli Naive Bayes | 0.784 |
| K-Nearest Neighbors | 0.877 |
| Logistic Regression | 0.804 |
| Decision Tree | 1.000 |
| Random Forest | 1.000 |

The **Random Forest Classifier** was selected as the final model, achieving a **test accuracy of ~91.9%**, along with a confusion matrix used to visualize prediction performance on the test set.

> Note: The Decision Tree and Random Forest models show perfect training accuracy, which suggests overfitting on the training set — something to keep in mind if extending this project (e.g., via cross-validation, hyperparameter tuning, or pruning).

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** pandas, numpy, matplotlib, seaborn, plotly, scikit-learn, yellowbrick

## 🚀 Getting Started

1. Clone the repository and navigate to the `Grand Project` folder.
2. Install the required dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly scikit-learn yellowbrick
   ```
3. Open and run the notebook:
   ```bash
   jupyter notebook "Project Credit Risk Assessment for Loan Approval.ipynb"
   ```

## 📄 Additional Documentation

See `Grand Project.pdf` for the full written project report and further explanation of the methodology and findings.

## 🔮 Possible Improvements

- Address class imbalance in the target variable (majority of applicants are non-defaulters).
- Apply cross-validation and hyperparameter tuning to reduce overfitting in tree-based models.
- Try additional evaluation metrics (precision, recall, F1, ROC-AUC) given the imbalanced classes.
- Perform feature importance analysis to identify the strongest predictors of default.
