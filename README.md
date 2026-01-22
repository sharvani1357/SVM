# 🏦 Smart Loan Approval System (SVM + Streamlit)

A complete **Streamlit web application** that predicts whether a loan applicant will be **Approved (Eligible)** or **Rejected (Not Eligible)** using **Support Vector Machine (SVM)** classification.

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

SVM/
├── app.py
├── requirements.txt
└── data/
└── raw/
└── loan.csv

yaml
Copy code

---

## ⚙️ Installation

### 1) Install Dependencies
```bash
pip install -r requirements.txt
2) Run the Streamlit App
If streamlit command is not working, run using:

bash
Copy code
python -m streamlit run app.py
📌 Input Fields in App
Users can enter:

Applicant Income (Number)

Loan Amount (Number)

Credit History (Yes/No)

Employment Status (Yes/No)

Property Area (Urban/Semiurban/Rural)

📊 Output
The app displays:

✅ Loan Approved (Green highlight)
❌ Loan Rejected (Red highlight)

Also shows:

Kernel used

Model Test Accuracy

Confidence Score (Probability)

💡 Business Explanation
The app provides a short explanation such as:

“Based on good credit history and stable income pattern, the applicant is likely to repay the loan.”

“Because the applicant has no credit history, the risk is higher and approval is less likely.”

📦 Dependencies
streamlit

pandas

numpy

scikit-learn

👩‍💻 Author
Smart Loan Approval System - SVM Classifier Project

yaml
Copy code

---

If you want, I can also generate your **requirements.txt** based on your code and give you a **GitHub upload steps** for Streamlit deployment.






