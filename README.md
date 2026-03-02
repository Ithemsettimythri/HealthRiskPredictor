🩺 Health Risk Predictor — Diabetes & Hypertension

An AI-powered Streamlit web app that predicts Diabetes and Hypertension risks, detects Hypoglycemia and Hypotension, and provides personalized health recommendations based on:

- Age group  
- Medical readings (BP, Sugar levels, BMI, etc.)  
- Reported symptoms  
- ML-based and reference-based health insights  

This project combines **Machine Learning models**, **Reference Health Datasets**, and **Symptom-based Suggestions** into one interactive, educational health assessment platform.

🚀 Features

✅ Predicts risk levels for **Diabetes** and **Hypertension** using ML models  
✅ Detects **Hypoglycemia** (low sugar) and **Hypotension** (low BP) automatically  
✅ Shows **color-coded parameter risk indicators** with reference ranges  
✅ Provides **personalized recommendations** from the dataset:
   - Lifestyle Tips 🏃‍♀️  
   - Self-Monitoring 🧭  
   - Medical Advice 🩺  
✅ Integrates **AI predictions + Medical Thresholds**  
✅ Generates a downloadable **Health Risk Report (CSV)**  
✅ Fully interactive UI built using **Streamlit**

🧠 System Workflow

1️⃣ User Input
The user enters:
- Demographics (Age, Gender, Medical History)
- Vitals (BP, Sugar levels, BMI, Heart Rate)
- Symptoms (multiple selectable)

2️⃣ Risk Prediction
The app:
- Uses pre-trained ML models for Diabetes and Hypertension  
- Compares inputs with age-wise medical reference values  
- Detects special cases like:
  - **Low Sugar → Hypoglycemia**
  - **Low BP → Hypotension**

3️⃣ Condition Determination
Based on model + reference checks:
- Classifies user as Low / Moderate / High Risk
- Identifies primary condition:
  - Diabetes / Hypertension / Hypoglycemia / Hypotension / Mixed

4️⃣ Suggestion Mapping
Retrieves accurate, non-repetitive suggestions from  
`age_specific_suggestions_dataset.csv` using:
Condition + Symptom + AgeGroup + RiskLevel

Suggestions are grouped into:
- Lifestyle Tip
- Self-Monitoring
- Medical Advice

5️⃣ Output Summary
Displays:
- 🎯 Model probabilities & final risk  
- 🩸 Parameter overview (with color-coded icons)  
- 💡 Personalized recommendations  
- 📄 Option to download report as CSV  

🗂️ Project Structure

HealthRiskPredictor/
│
├── app.py
├── train_diabetes.py
├── train_hypertension.py                                # Main Streamlit application
├── requirements.txt                      # Required Python packages
│
├── models/                               # ML models and scalers
│   ├── diabetes_model.joblib
│   ├── diabetes_scaler.joblib
│   ├── diabetes_imputer.joblib
│   ├── hypertension_model.joblib
│   ├── hypertension_scaler.joblib
│   ├── hypertension_imputer.joblib
│
├── data/                                 # Reference & suggestion datasets
│   ├── expanded_reference_dataset.csv
│   ├── age_specific_suggestions_dataset.csv
│   ├── symptom_dataset_cleaned.csv
│   ├── Diabetes_1000_based_on_previous_rows.csv
│   ├── Expanded_Hypertension_1000.csv
│
└── README.md                             # Documentation

⚙️ Local Installation Guide

1️⃣ Clone the Repository

git clone https://github.com/your-username/HealthRiskPredictor.git
cd HealthRiskPredictor


2️⃣ Create a Virtual Environment (Recommended)

python -m venv venv
source venv/bin/activate       # For macOS/Linux
venv\Scripts\activate          # For Windows

3️⃣ Install Dependencies

pip install -r requirements.txt

4️⃣ Run the Streamlit App

streamlit run app.py

Then open your browser at [http://localhost:8501](http://localhost:8501).

☁️ Deployment on Streamlit Cloud

1. Push all your project files to a **GitHub repository**.
2. Go to [https://share.streamlit.io](https://share.streamlit.io).
3. Click “New App”.
4. Connect your GitHub account and repository.
5. Set:

   Main file path:`app_streamlit.py`
   Branch: `main` (or your working branch)
6. Click Deploy🎉

Your app will be live at:

https://yourusername-healthriskpredictor.streamlit.app/

🧾 requirements.txt

streamlit==1.36.0
pandas==2.2.3
numpy==2.1.3
scikit-learn==1.5.2
joblib==1.4.2
# PDF Export
reportlab==4.2.2
# Optional (for better visuals or markdown safety)
tabulate==0.9.0
# Ensure regex handling
regex==2024.9.11

🎨 Risk Color Legend

| Icon | Risk Level   | Description                                   |
| ---- | ------------ | --------------------------------------------- |
| 🔴   | **High**     | Immediate medical attention may be required   |
| 🟡   | **Moderate** | Needs close monitoring                        |
| 🟢   | **Normal**   | Healthy range                                 |
| 🔵   | **Low**      | Indicates **Hypoglycemia** or **Hypotension** |
| ⚪    | **Unknown**  | Insufficient data or missing reference        |

🧩 Technologies Used

Python 3.10+
Streamlit – for frontend & app logic
scikit-learn – for ML models (SVM, KNN )
pandas / numpy– for data processing
joblib – for loading models and scalers


Each model is trained separately and integrated via preprocessing (imputer + scaler).

🩸 Parameter Evaluation Rules

| Parameter     | Normal Range | Low    | High  |
| ------------- | ------------ | ------ | ----- |
| Systolic BP   | 90–120 mmHg  | < 90   | > 140 |
| Diastolic BP  | 60–80 mmHg   | < 60   | > 90  |
| Fasting Sugar | 70–99 mg/dL  | < 70   | > 126 |
| Random Sugar  | 70–140 mg/dL | < 70   | > 200 |
| BMI           | 18.5–24.9    | < 18.5 | > 30  |

Low BP/Sugar automatically indicates **Hypotension / Hypoglycemia**.

📊 Output Example

🧮 Input:

| Parameter     | Value             |
| ------------- | ----------------- |
| Age           | 45                |
| Gender        | Female            |
| Systolic BP   | 145               |
| Fasting Sugar | 160               |
| BMI           | 29                |
| Symptoms      | Fatigue, Headache |

🩺 Output:

**Condition:** Diabetes
**Risk:** 🔴 High

**Suggestions:**

* Lifestyle Tip: Reduce sugar intake and engage in light physical activity.
* Self-Monitoring: Check blood sugar twice daily.
* Medical Advice: Consult your physician for medication adjustment.

⚠️ Disclaimer

> This application is designed **for educational and informational purposes only.**
> It **does not provide medical advice** or replace a doctor’s consultation.
> Always consult a **certified healthcare provider** for professional diagnosis and treatment.

👩‍💻 Developer Info

👩‍💻 Developer Info

**Developed by:** *Mythri Ithemsetti*  
**Project Title:** *AI-Based Health Risk Prediction System*  
**Domain:** Artificial Intelligence & Healthcare  
**Year:** 2025

© 2025 — *All Rights Reserved.*
