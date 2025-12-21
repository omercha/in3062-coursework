# IN3062 Coursework – Running the Project

This repository contains Jupyter notebooks for the IN3062 Introduction to Artificial Intelligence coursework.

## How to download
1. Click **Code** → **Download ZIP**
2. Extract the ZIP folder to a location on your computer

## Requirements
- Python 3.x installed
- Jupyter Notebook or JupyterLab installed  
  (If needed: `pip install notebook` or `pip install jupyterlab`)

You will also need the libraries used in the notebooks (pandas, numpy, scikit-learn, matplotlib, seaborn, joblib).

## Notebook run order (important)
Open "in3062-coursework" and please run the notebooks in this order:

1. **01_data_preparation_and_baseline.ipynb**  
   - Loads the raw CSV files  
   - Creates the merged dataset  
   - Creates the train/validation/test splits (`X_train`, `X_val`, `X_test`, `y_train`, `y_val`, `y_test`)  
   - Saves outputs into the `data/` folder

2. **EDA.ipynb** (in folder `Test/`)  
   - Exploratory data analysis on the merged dataset and target variable

3. **02_model_decision_tree.ipynb**  
   - Trains and evaluates the Decision Tree model using the saved splits

4. **03_svm_model.ipynb** (in folder `Test/`)  
   - Trains and evaluates the SVM model using the saved splits

5. **04_random_forest_model.ipynb** (in folder `Test/`)  
   - Trains and evaluates the Random Forest model using the saved splits

## Notes about folders
- `Test/` contains:
  - `EDA.ipynb`
  - `03_svm_model.ipynb`
  - `04_random_forest_model.ipynb`

- `data/` is created/filled by Notebook 01 and contains:
  - `merged_credit_data.csv`
  - `X_train.csv`, `X_val.csv`, `X_test.csv`
  - `y_train.csv`, `y_val.csv`, `y_test.csv`

## Common issues / troubleshooting
- **FileNotFoundError for CSVs:**  
  Ensure the raw dataset CSVs are in the folder/path used inside `01_data_preparation_and_baseline.ipynb`.

- **Notebooks run slowly:**  
  Some models (especially SVM and Random Forest) can take time depending on machine speed.

- **Package/module not found:**  
  Install missing packages using:  
  `pip install pandas numpy scikit-learn matplotlib seaborn joblib`
