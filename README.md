[README.md](https://github.com/user-attachments/files/27994588/README.md)
# 🎓 Student Placement Prediction — End-to-End Machine Learning Project

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3+-orange?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Overview

This project builds a complete **end-to-end Machine Learning pipeline** on a synthetic dataset
of **100,000 engineering students** to solve two real-world problems:

| Task | Type | Question Answered |
|---|---|---|
| 🎯 Placement Prediction | Classification | Will this student get placed? (Yes / No) |
| 💰 Salary Estimation | Regression | What salary package can they expect? (in LPA) |

The entire project is built in **Python** inside a **Jupyter Notebook** using industry-standard
libraries — making it beginner-friendly with detailed code comments explaining every step.

---

## 📊 Dataset

| Detail | Info |
|---|---|
| Total Records | 100,000 students |
| Total Features | 18 features per student |
| Placed Students | 68,475 (68.5%) |
| Not Placed | 31,525 (31.5%) |
| Salary Range | 6.88 LPA — 28.33 LPA |
| Mean Salary | 17.31 LPA |

### 🧾 Features

| Feature | Type | Description |
|---|---|---|
| `branch` | Categorical | Engineering branch (CSE, IT, ECE, EE, ME, CE, Chemical) |
| `college_tier` | Categorical | College ranking (Tier-1, Tier-2, Tier-3) |
| `cgpa` | Float | Cumulative Grade Point Average |
| `backlogs` | Integer | Number of failed subjects |
| `coding_skills` | Float | Coding proficiency score |
| `dsa_score` | Float | Data Structures & Algorithms score |
| `aptitude_score` | Float | Aptitude test score |
| `communication_skills` | Float | Communication proficiency score |
| `ml_knowledge` | Float | Machine Learning knowledge score |
| `system_design` | Float | System design proficiency score |
| `internships` | Integer | Number of internships completed |
| `projects_count` | Integer | Number of projects completed |
| `certifications` | Integer | Number of certifications earned |
| `hackathons` | Integer | Hackathon participations |
| `open_source_contributions` | Integer | Open source contributions |
| `extracurriculars` | Integer | Extra-curricular activities |
| `placement_status` | Target (0/1) | Whether student was placed |
| `salary_package_lpa` | Target (Float) | Salary offered (placed students only) |

---

## 🛠️ Tech Stack

```
Language   : Python 3.10+
Environment: Jupyter Notebook
Libraries  : pandas, numpy, scikit-learn, matplotlib, seaborn, joblib
```

---

## 🤖 Models Trained & Results

### Task 1 — Classification (Placement Prediction)

| Model | Accuracy |
|---|---|
| Logistic Regression | 69.94% |
| Random Forest Classifier | 69.29% |
| Gradient Boosting Classifier | **69.87% ⭐** |

### Task 2 — Regression (Salary Estimation)

| Model | MAE (LPA) | R² Score |
|---|---|---|
| Linear Regression | 0.9869 | 0.7734 |
| Random Forest Regressor | 1.0139 | 0.7601 |
| Gradient Boosting Regressor | **0.9704 ⭐** | **0.7798 ⭐** |

> ⭐ Best performing model for each task

---

## 🔍 Key Findings

- **CGPA** is the single most important feature for placement prediction (11.7% importance)
- **Aptitude Score** and **DSA Score** are the next most influential features
- **CSE and IT** branches have the highest placement rates
- **Tier-1** college students significantly outperform Tier-2 and Tier-3 peers
- Students with **0 backlogs** dominate the placed cohort
- All skill scores (coding, ML, system design, communication) contribute roughly equally

---

## 📁 Project Structure

```
student-placement-ml/
│
├── 📓 student_placement_ML.ipynb       # Main Jupyter Notebook
├── 📊 student_placement_synthetic.csv  # Dataset
│
├── 📦 placement_classifier.pkl         # Saved Classification Model
├── 📦 salary_regressor.pkl             # Saved Regression Model
├── 📦 scaler_classifier.pkl            # Saved Scaler (Classification)
├── 📦 scaler_regressor.pkl             # Saved Scaler (Regression)
├── 📦 feature_columns.pkl              # Saved Feature Column Names
│
└── 📄 README.md                        # This file
```

---

## 🚀 How to Run Locally

### Step 1 — Clone the Repository
```bash
git clone https://github.com/yourusername/student-placement-ml.git
cd student-placement-ml
```

### Step 2 — Install Required Libraries
```bash
pip install pandas numpy scikit-learn matplotlib seaborn joblib jupyter
```

### Step 3 — Launch Jupyter Notebook
```bash
jupyter notebook
```

### Step 4 — Open and Run
- Open `student_placement_ML.ipynb`
- Click **Run All** from the Cell menu
- All outputs, charts, and model results will appear automatically

---

## 🧪 Test With Your Own Input

You can predict placement and salary for any student profile:

```python
my_student = {
    'college_tier':              'Tier-2',
    'branch':                    'CSE',
    'cgpa':                       8.5,
    'backlogs':                   0,
    'coding_skills':              7.5,
    'dsa_score':                  7.0,
    'aptitude_score':             7.5,
    'communication_skills':       8.0,
    'ml_knowledge':               6.0,
    'system_design':              6.5,
    'internships':                1,
    'projects_count':             3,
    'certifications':             2,
    'hackathons':                 1,
    'open_source_contributions':  0,
    'extracurriculars':           2
}

predict_student(my_student)
```

### Sample Output
```
=============================================
       🎓 STUDENT PLACEMENT PREDICTION
=============================================
  ✅ Placement Status  : PLACED
  📊 Placement Chance  : 84.3%
  💰 Expected Salary   : ₹ 19.72 LPA
=============================================
```

---

## 📈 Project Workflow

```
Raw CSV Data
     │
     ▼
Data Exploration & Visualization
     │
     ▼
Data Preprocessing
(Encoding → Splitting → Scaling)
     │
     ▼
Model Training & Comparison
(3 Classifiers + 3 Regressors)
     │
     ▼
Model Evaluation
(Accuracy, R², MAE, F1-Score)
     │
     ▼
Save Models (.pkl files)
     │
     ▼
Prediction Function
(Input any student → Get placement & salary)
```

---

## 🔗 Links

- 📓 **Kaggle Notebook:** [View on Kaggle](https://kaggle.com/code/nivashnandan07/student-placement-prediction)
- 📊 **Dataset:** [View Dataset](https://kaggle.com/datasets/suhanigupta04/student-placement-dataset)

---

## 🙋 About

This project was built as an independent Machine Learning project to demonstrate
a complete ML workflow from raw data to deployable prediction function.
**Connect with me:**

[![LinkedIn](www.linkedin.com/in/nivash-nandan-b0b63729b)

[![Kaggle](https://img.shields.io/badge/Kaggle-Follow-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://kaggle.com/nivashnandan07)

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

⭐ **If you found this project helpful, please give it a star!** ⭐
