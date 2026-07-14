
# Titanic Survivor Prediction

A machine learning project that predicts whether a Titanic passenger survived, based on features like age, sex, fare, passenger class, and port of embarkation, using a Decision Tree classifier.

## 📁 Project Structure

```
Titanic task/
├── Titanic Surviver Prediction.ipynb   # Main notebook — data cleaning & model
├── Titanic.csv                         # Dataset
└── readme.md
```

## 📊 Dataset

`Titanic.csv` contains 1,309 passenger records. After trimming the raw file down to the relevant columns, the notebook works with:

| Column | Description |
|---|---|
| `Passengerid` | Unique passenger identifier |
| `Age` | Passenger's age |
| `Fare` | Ticket fare paid |
| `Sex` | Passenger's sex (encoded: 0/1) |
| `sibsp` | Number of siblings/spouses aboard |
| `Pclass` | Ticket class (1st, 2nd, 3rd) |
| `Embarked` | Port of embarkation (encoded) |
| `Survived` | Target variable — 1 if the passenger survived, 0 otherwise |

## 🔍 Project Workflow

1. **Load the data** and select the relevant subset of columns (`Passengerid`, `Age`, `Fare`, `Sex`, `sibsp`, `Pclass`, `Embarked`, `Survived`).
2. **Handle missing values** — 2 missing values in `Embarked` were filled using the column's median.
3. **Feature/target split**
   - Target: `Survived`
   - Features used for modeling: `Passengerid`, `Age`, `Sex`, `Pclass` (`sibsp`, `Embarked`, and `Fare` were dropped from the final feature set).
4. **Encoding** — categorical/numeric fields (`Passengerid`, `Age`, `Sex`, `Pclass`) were transformed with `LabelEncoder`.
5. **Model training** — a `DecisionTreeClassifier` (from scikit-learn) was trained on the encoded features (`Age`, `Sex`, `Pclass`).
6. **Evaluation & prediction** — checked training accuracy, then used the model to predict survival for new, hand-crafted passenger examples.

## 📈 Results

- **Training accuracy:** ~85.0%
- Example predictions on new inputs (features: age, sex, class):
  - Age 53, male, 2nd class → predicted **did not survive**
  - Age 60, female, 2nd class → predicted **did not survive**

> Note: the accuracy above is measured on the training data itself (no separate train/test split was used), so it likely overstates how well the model would perform on unseen passengers.

## 🛠️ Tech Stack

- **Language:** Python
- **Libraries:** pandas, numpy, matplotlib, scikit-learn

## 🚀 Getting Started

1. Clone the repository and navigate to the `Titanic task` folder.
2. Install the required dependencies:
   ```bash
   pip install pandas numpy matplotlib scikit-learn
   ```
3. Open and run the notebook:
   ```bash
   jupyter notebook "Titanic Surviver Prediction.ipynb"
   ```
   > Note: the notebook reads the dataset from a `Task/` subfolder (`Task/Titanic.csv`). Adjust the file path if your CSV is in the project root instead.

## 🔮 Possible Improvements

- Split the data into train/test sets to get a more realistic estimate of model performance.
- Include additional features (e.g. `Fare`, `sibsp`, `Embarked`) that were dropped before modeling.
- Compare the Decision Tree against other classifiers (Logistic Regression, Random Forest, etc.).
- Tune tree depth/parameters to reduce the risk of overfitting.
