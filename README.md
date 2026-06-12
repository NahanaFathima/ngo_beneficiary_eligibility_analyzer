# 🤝 NGO Beneficiary Eligibility Analyzer

An AI-powered system that helps NGOs identify eligible beneficiaries for support programs using Machine Learning.

---

## 📋 Project Overview

Many NGOs provide support such as Educational Scholarships, Food Assistance, Medical Aid, and Skill Development Programs. Manually identifying eligible beneficiaries is time-consuming and error-prone. This application automates the process using a trained Machine Learning model that predicts eligibility based on applicant information.

---

## 🚀 Features Implemented

- ✅ Synthetic beneficiary dataset generation (200 records)
- ✅ Data preprocessing with Label Encoding
- ✅ Decision Tree and Random Forest model training
- ✅ Model evaluation (Accuracy, Precision, Recall, Confusion Matrix)
- ✅ Eligibility prediction with confidence score
- ✅ FastAPI REST backend with full CRUD operations
- ✅ Data visualizations (4 charts)
- ✅ Streamlit interactive UI with dark theme

---

## 🧠 Machine Learning Algorithm

| Model | Accuracy | Precision | Recall |
|---|---|---|---|
| Decision Tree | 100% | 100% | 100% |
| **Random Forest** | **100%** | **100%** | **100%** |

**Best Model: Random Forest Classifier**
- 100 decision trees voting together
- Trained on 160 samples, tested on 40 samples
- Saved as `model/best_model.pkl`

### Eligibility Rules Used
- Family Income < ₹1,50,000 → **Eligible**
- Employment Status = Unemployed → **Eligible**
- Disability Status = Yes → **Eligible**
- Otherwise → **Not Eligible**

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3.x |
| ML Library | Scikit-Learn |
| Data Processing | Pandas, NumPy |
| Backend API | FastAPI, Uvicorn |
| Frontend UI | Streamlit |
| Visualization | Matplotlib, Seaborn |
| Model Saving | Joblib |

---

## 📁 Project Structure

```
ngo_eligibility_analyzer/
│
├── data/
│   ├── beneficiaries.csv       ← Dataset
│   └── charts/                 ← Generated visualizations
│
├── model/
│   ├── best_model.pkl          ← Trained Random Forest model
│   ├── encoders.pkl            ← Label encoders
│   ├── X_test.pkl              ← Test features
│   └── y_test.pkl              ← Test labels
│
├── dataset.py                  ← Dataset generation
├── preprocess.py               ← Data preprocessing
├── train.py                    ← Model training
├── evaluate.py                 ← Model evaluation
├── predict.py                  ← Prediction logic
├── visualize.py                ← Chart generation
├── main.py                     ← FastAPI backend
├── app.py                      ← Streamlit UI
├── requirements.txt            ← Dependencies
└── README.md
```

---

## ⚙️ Setup Instructions

### 1. Clone or download the project
```bash
cd ngo_eligibility_analyzer
```

### 2. Create and activate virtual environment
```bash
python -m venv venv

# Windows PowerShell
.\venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Generate dataset
```bash
python dataset.py
```

### 5. Train the model
```bash
python train.py
```

### 6. Generate visualizations
```bash
python visualize.py
```

### 7. Run FastAPI backend
```bash
uvicorn main:app --reload
```
API available at: `http://localhost:8000`
API Docs at: `http://localhost:8000/docs`

### 8. Run Streamlit UI (in a new terminal)
```bash
streamlit run app.py
```
UI available at: `http://localhost:8501`

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Welcome message |
| GET | `/beneficiaries` | Get all records |
| GET | `/beneficiaries/{id}` | Get record by ID |
| POST | `/beneficiaries` | Add new record |
| PUT | `/beneficiaries/{id}` | Update record |
| DELETE | `/beneficiaries/{id}` | Delete record |
| POST | `/train` | Train the model |
| POST | `/predict` | Predict eligibility |
| GET | `/analytics` | Get summary stats |

### Sample Predict Request
```json
POST /predict
{
  "age": 22,
  "family_income": 120000,
  "family_members": 5,
  "employment_status": "Unemployed",
  "education_level": "Undergraduate",
  "disability_status": "No"
}
```

### Sample Predict Response
```json
{
  "prediction": "Eligible",
  "confidence": 0.96
}
```

---

## 📦 Requirements

```
fastapi
uvicorn
pandas
numpy
scikit-learn
matplotlib
seaborn
joblib
pydantic
streamlit
```

---

## 👩‍💻 Author
Nahana Fathima
NGO Beneficiary Eligibility Analyzer — AI + Python Task 2
