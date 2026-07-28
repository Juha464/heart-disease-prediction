# ❤️ Heart Disease Prediction

A machine learning project that predicts the likelihood of heart disease or heart attack using health indicators from the BRFSS 2015 survey dataset. Includes data cleaning, exploratory analysis, class imbalance handling, and comparison of multiple classification models.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)

---

## 📋 Overview

Cardiovascular disease is one of the leading causes of death worldwide. This project uses the **BRFSS 2015 Heart Disease Health Indicators** dataset (253,680 patient records, 22 features) to explore which health and lifestyle factors are most associated with heart disease, and to build classification models that predict heart disease risk.

## 🎯 Features

- Data loading and inspection (`.info()`, `.describe()`, null checks)
- Feature scaling with `StandardScaler`
- Exploratory data analysis: correlation heatmap, BMI distribution, high blood pressure/cholesterol distributions, and their relationship with heart disease
- Class imbalance handling using **SMOTE** (oversampling)
- Model comparison: Logistic Regression, Decision Tree, Random Forest
- Hyperparameter tuning with `GridSearchCV`
- Feature importance analysis

## 🗂️ Dataset

- **Source:** BRFSS 2015 Heart Disease Health Indicators dataset (`heart_disease_health_indicators_BRFSS2015.csv`)
- **Size:** 253,680 rows × 22 columns, no missing values
- **Target:** `HeartDiseaseorAttack` (0 = no heart disease/attack, 1 = has had heart disease/attack) — imbalanced, ~9.4% positive class
- **Features used for modeling:** `HighBP`, `HighChol`, `BMI` (a reduced subset selected from the full 21 available indicators, which also include Smoker, Stroke, Diabetes, PhysActivity, GenHlth, Age, Income, Education, etc.)

## 🚀 How to Run

This project was developed in Google Colab. To run it locally:

```bash
# Clone the repository
git clone https://github.com/Juha464/heart-disease-prediction.git
cd heart-disease-prediction

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn

# Launch the notebook
jupyter notebook
```

You'll need the BRFSS 2015 CSV file (`heart_disease_health_indicators_BRFSS2015.csv`) available to the notebook — the original workflow uploads it interactively via Google Colab's file picker.

## 📊 Results

Because `HeartDiseaseorAttack` is heavily imbalanced (~91% negative, ~9% positive), raw accuracy is misleading. SMOTE was applied to the training data to balance classes before retraining.

**After SMOTE (on original test set):**

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Logistic Regression | 64% | 17% | 71% | 27% |
| Decision Tree | 67% | 18% | 68% | 28% |
| Random Forest | 67% | 18% | 68% | 28% |

**Tuned Decision Tree** (via `GridSearchCV`, best params: `criterion='gini'`, `max_depth=10`, `min_samples_split=2`, `min_samples_leaf=1`):

| Metric | Score |
|---|---|
| Accuracy | 65% |
| Precision (positive class) | 17% |
| Recall (positive class) | 71% |
| F1 Score (positive class) | 28% |

**Feature importance (tuned Decision Tree):**

| Feature | Importance |
|---|---|
| HighBP | 74.6% |
| HighChol | 22.2% |
| BMI | 3.1% |

`HighBP` (high blood pressure) is by far the strongest predictor of heart disease/attack in this feature set, followed by `HighChol`.

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- scikit-learn (LogisticRegression, DecisionTreeClassifier, RandomForestClassifier, GridSearchCV, StandardScaler)
- imbalanced-learn (SMOTE)
- Matplotlib / Seaborn
- Jupyter Notebook / Google Colab

## 📁 Project Structure

```
heart-disease-prediction/
├── Pds_Project.ipynb      # main analysis & model notebook
└── README.md
```

## 📌 Future Improvements

- Use the full set of 21 available features rather than just 3, and compare performance
- Try additional models (XGBoost, SVM) and ensemble approaches
- Address the precision/recall tradeoff further — current models favor recall over precision, which may or may not suit the intended use case
- Add a `requirements.txt` and move the dataset loading out of the interactive Colab upload flow so the notebook runs end-to-end locally
- Deploy as a simple web app (Streamlit/Flask) for interactive predictions

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
