# ❤️ Heart Disease Prediction

A machine learning model that predicts the likelihood of heart disease in a patient based on clinical and demographic health data. Built to explore how classification models can support early risk detection.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)

---

## 📋 Overview

Cardiovascular disease is one of the leading causes of death worldwide. This project uses a dataset of patient health metrics (age, cholesterol, blood pressure, etc.) to train a classification model that predicts whether a patient is at risk of heart disease.

## 🎯 Features

- Data cleaning & exploratory data analysis (EDA)
- Feature correlation analysis and visualization
- Model training using [e.g. Logistic Regression / Random Forest — *update with your actual model*]
- Performance evaluation with accuracy, precision, recall, and confusion matrix

## 🗂️ Dataset

- **Source:** *(add dataset source/link here, e.g. UCI Heart Disease Dataset)*
- **Features used:** age, sex, chest pain type, resting blood pressure, cholesterol, fasting blood sugar, max heart rate, etc.
- **Target:** presence (1) or absence (0) of heart disease

## 🚀 How to Run

```bash
# Clone the repository
git clone https://github.com/Juha464/heart-disease-prediction.git
cd heart-disease-prediction

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook
```

## 📊 Results

| Metric | Score |
|---|---|
| Accuracy | 87% *(example — replace with your real result)* |
| Precision | 0.85 |
| Recall | 0.83 |
| F1-Score | 0.84 |

*(Add a confusion matrix image or ROC curve screenshot here for extra visual impact — drag an image into the repo and reference it like `![confusion matrix](images/confusion_matrix.png)`)*

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- scikit-learn
- Matplotlib / Seaborn
- Jupyter Notebook

## 📁 Project Structure

```
heart-disease-prediction/
├── data/                  # dataset files
├── notebook.ipynb         # main analysis & model notebook
├── requirements.txt       # dependencies
└── README.md
```

## 📌 Future Improvements

- Hyperparameter tuning for improved accuracy
- Deploy as a simple web app (Streamlit/Flask)
- Test additional models (XGBoost, SVM)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
