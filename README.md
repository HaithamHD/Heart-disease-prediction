# ❤️ Cardiovascular Disease Prediction

A machine learning project that predicts whether a patient has cardiovascular disease from basic vital signs and lifestyle data, using a **Random Forest** classifier.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)

## 📌 Problem

Heart disease is the leading cause of death worldwide. Traditional diagnosis depends on physician expertise and clinical tests, which can be time-consuming and prone to human error. This project builds a classification model that can act as an assistant to help doctors with early detection.

## 📊 Dataset

- **Source:** [Cardiovascular Disease dataset – Kaggle](https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset)
- **Size:** 70,000 patient records
- **Features:** 11 input features + 1 target
- **Classes:** 2 (`0` = Healthy, `1` = Cardiovascular disease)

| Feature | Column | Type |
|---|---|---|
| Age | `age` | int (days → converted to years) |
| Height | `height` | int (cm) |
| Weight | `weight` | float (kg) |
| Gender | `gender` | categorical |
| Systolic blood pressure | `ap_hi` | int |
| Diastolic blood pressure | `ap_lo` | int |
| Cholesterol | `cholesterol` | 1: normal, 2: above normal, 3: well above normal |
| Glucose | `gluc` | 1: normal, 2: above normal, 3: well above normal |
| Smoking | `smoke` | binary |
| Alcohol intake | `alco` | binary |
| Physical activity | `active` | binary |
| **Target** | `cardio` | binary |

## ⚙️ Workflow

1. **Data exploration** – shape, missing values, statistics
2. **Preprocessing**
   - Dropped the `id` column
   - Removed unrealistic blood pressure readings (70,000 → 68,759 records)
   - Encoded gender as 0/1 and converted age from days to years
3. **Train/test split** – 80% / 20%
4. **Scaling** – `StandardScaler`
5. **Model** – `RandomForestClassifier(n_estimators=100, max_depth=15)`
6. **Evaluation & visualization** – metrics and confusion matrix

## 📈 Results

| Metric | Score |
|---|---|
| Accuracy | **73.5%** |
| Precision | 75.7% |
| Recall | 68.2% |
| F1-score | 71.7% |

**Strengths:** Random Forest reduces overfitting compared to a single decision tree and handles a large dataset well.

**Limitations:** Some overlap between healthy and ill patients in blood pressure readings causes misclassification. Adding more lifestyle features (diet, stress) could improve results.

## 🚀 How to Run

```bash
git clone https://github.com/HaithamHD/Heart-disease-prediction.git
cd Heart-disease-prediction
pip install -r requirements.txt
```

1. Download `cardio_train.csv` from the [Kaggle dataset page](https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset).
2. Place it in the same folder as the notebook.
3. Open `AI_Final_Project_Heart_Disease.ipynb` in Jupyter Notebook, VS Code or Google Colab and run all cells.

## 👥 Team

- Haitham Hani Dalloul

*Final project for the Artificial Intelligence course – Al-Aqsa University.*
