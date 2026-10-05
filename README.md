# Public Health Data Analysis: Diabetes Prediction

Exploratory data analysis and prediction using open health data.

## Objective
This project analyzes a public health dataset to find which medical
measurements are linked to diabetes, and compares two machine learning
models that predict whether a patient has diabetes.

## Data
- Source: Pima Indians Diabetes Database, accessed through Kaggle
  (https://www.kaggle.com/datasets/mragpavank/diabetes). The data was
  originally collected by the National Institute of Diabetes and
  Digestive and Kidney Diseases.
- Size: 768 patients, 8 medical measurements and one target (`Outcome`)
- Population: women of Pima Indian heritage, aged 21 and older

## Methods
- Found hidden missing values (zeros in Glucose, BloodPressure,
  SkinThickness, Insulin and BMI) and replaced them with NaN
- Exploratory analysis with histograms, box plots and a correlation
  heatmap
- Stratified 80/20 train/test split
- Missing values filled with the median inside a pipeline (no data
  leakage)
- Logistic Regression and Random Forest, compared with 5-fold
  cross-validation
- Evaluation with ROC AUC, precision, recall, F1-score and confusion
  matrix

## Results
| Model | CV ROC AUC | Test ROC AUC | Test accuracy | Diabetes recall |
|---|---|---|---|---|
| Logistic Regression | 0.844 | 0.813 | 0.73 | 0.70 |
| Random Forest | 0.823 | 0.817 | 0.74 | 0.56 |

- Glucose is the measurement most strongly linked to diabetes
  (correlation 0.49), followed by BMI and Insulin.
- Both models perform similarly. Logistic Regression finds more
  patients with diabetes, while Random Forest gives fewer false alarms.

## Limitations
- Small dataset (768 patients); the test set has only 154 patients.
- Only Pima women aged 21+, so results may not apply to other groups.
- Many Insulin and SkinThickness values were missing and were filled
  with the median.
- Models were not tuned in depth. This project is for learning purposes
  and is not a medical tool.

## Tools
Python, pandas, NumPy, matplotlib, seaborn, scikit-learn, Google Colab

## How to run
1. Clone this repository
2. Install the requirements: `pip install -r requirements.txt`
3. Open `diabetes_prediction_eda_and_ml.ipynb` in Jupyter or Google
   Colab (keep `diabetes.csv` in the same folder)

## Author
Khadim Hussain
