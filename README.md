# 🏦 Smart Loan Approval System (SVM + Streamlit)

A complete **Streamlit web application** that predicts whether a loan applicant will be **Approved (Eligible)** or **Rejected (Not Eligible)** using **Support Vector Machine (SVM)** classification.

### https://sharvani1357-svm-app-1wsubv.streamlit.app/

This project allows users to enter applicant details and get a real-time loan decision using different SVM kernels.

---

## 📌 Project Features

✅ **Loan Approval Prediction (Real-Time)**  
Users enter applicant details and the model predicts loan eligibility instantly.

✅ **Multiple Kernel Selection (Kernel Understanding)**  
- Linear SVM  
- Polynomial SVM  
- RBF SVM  

✅ **Model Confidence (Optional)**  
Displays prediction confidence using probability scores.

✅ **Business Explanation (Very Important)**  
Shows a short reasoning message explaining why approval/rejection happened.

---

## 🧠 ML Workflow Used

1. **Data Loading**
   - Reads dataset from `data/raw/loan.csv`

2. **Data Cleaning**
   - Missing values handled using:
     - Mode for categorical columns  
     - Median for numeric columns  
   - Drops `Loan_ID` column (not useful for prediction)

3. **Feature Selection**
   The app uses only these columns:
   - ApplicantIncome  
   - LoanAmount  
   - Credit_History  
   - Self_Employed  
   - Property_Area  
   - Loan_Status (Target)

4. **Encoding**
   - Target `Loan_Status` is encoded:
     - Y → 1  
     - N → 0  
   - Categorical features are converted using **One-Hot Encoding**

5. **Scaling**
   - Uses **StandardScaler**
   - Required for SVM because SVM depends on distance calculations

6. **Model Training**
   - Trains SVM model using selected kernel:
     - Linear / Poly / RBF

7. **Prediction**
   - Predicts Loan Status
   - Shows:
     - Loan Approved / Loan Rejected
     - Kernel used
     - Accuracy
     - Confidence score

---

## 📁 Project Structure

### SVM/
### ├── app.py
### ├── requirements.txt
### └── data/
###  └── raw/
###   └── loan.csv


---

## ⚙️ Installation

### 1) Install Dependencies
  ### pip install -r requirements.txt


## Run the Streamlit App

### If streamlit command is not working, run using:

### python -m streamlit run app.py



## 📌 Input Fields (User Inputs)

The application allows the user to enter the following applicant details:

- **Applicant Income** (Number Input)
- **Loan Amount** (Number Input)
- **Credit History** (Yes / No)
- **Employment Status (Self Employed)** (Yes / No)
- **Property Area** (Urban / Semiurban / Rural)

---

## 🎯 Model Selection

The user can select the SVM kernel using a radio button:

- **Linear SVM**
- **Polynomial SVM**
- **RBF SVM**

This helps in understanding how different kernels affect prediction performance.

---

## 🔘 Prediction Button

Click the button below to generate the result:

✅ **Check Loan Eligibility**

---

## 📊 Output (Prediction Result)

The application displays the result clearly as:

✅ **Loan Approved** (Green Highlight)  
❌ **Loan Rejected** (Red Highlight)

It also shows additional information:

- **Kernel Used**
- **Model Test Accuracy**
- **Confidence Score (Probability)** *(Optional)*

---

## 💡 Business Explanation

The app provides a short business-level explanation such as:

- “Based on good credit history and stable income pattern, the applicant is likely to repay the loan.”
- “Because the applicant has no credit history, the risk is higher and approval is less likely.”

This helps users understand the reason behind approval or rejection.
