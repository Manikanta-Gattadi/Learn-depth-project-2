# Learn-depth-project-2
🎓 Student Placement Eligibility Predictor

Binary Classification using Logistic Regression

A machine learning project that uses Logistic Regression to predict a student's placement-related outcome based on their academic performance and extracurricular profile.

«Note: The dataset's documentation does not definitively establish whether target class "1" means "eligible" or "not eligible." The model coefficients suggest that class "1" may instead represent an at-risk/not-eligible outcome. This should be confirmed against the original assignment brief before interpreting predictions as eligibility.»

---

📌 Project Overview

The objective of this project is to build a binary classification model that predicts the target outcome for students using academic and activity-related features.

The project uses Logistic Regression, which estimates the probability of a student belonging to the positive class and converts that probability into a binary prediction.

The dataset contains 1,000 student records with six input features and a binary target variable.

---

📊 Dataset

Dataset: "dataset_07_student_placement_eligibility.csv"

Feature| Description
"cgpa"| Student's CGPA
"attendance_pct"| Attendance percentage
"coding_score"| Coding assessment score
"projects_completed"| Number of completed projects
"internship_months"| Duration of internship experience
"backlogs"| Number of academic backlogs
Target| Binary classification target

Dataset Statistics

- Total records: 1,000
- Input features: 6
- Target classes: 2
- Class 0: 500 records
- Class 1: 500 records
- Missing values: None
- Duplicate rows: None

---

🔄 Machine Learning Workflow

Dataset
   ↓
Data Quality Check
   ↓
Train/Test Split
   ↓
Feature Scaling
   ↓
Logistic Regression
   ↓
Prediction
   ↓
Model Evaluation

1. Data Quality Check

The dataset was checked for:

- Missing values
- Duplicate records
- Invalid feature ranges
- Class imbalance

No cleaning was required because the dataset contained no missing values or duplicate rows and the feature values were within sensible ranges.

2. Train-Test Split

The data was divided into:

- 80% training data: 800 students
- 20% testing data: 200 students

A stratified split was used to preserve the 50/50 class distribution in both datasets.

3. Feature Scaling

"StandardScaler" was applied to standardize the input features.

The scaler was fitted only on the training data and then applied to the test data to prevent data leakage.

4. Model

The project uses Logistic Regression with:

Solver: lbfgs
max_iter: 1000
random_state: 42

The fixed random state ensures that the experiment is reproducible.

---

📈 Model Performance

The model was evaluated on 200 unseen test records.

Metric| Score
Accuracy| 70%
Precision| 69%
Recall| 73%
F1-Score| 71%
ROC-AUC| 0.79

Confusion Matrix

| Predicted Negative| Predicted Positive
Actual Negative| 67| 33
Actual Positive| 27| 73

- True Negatives: 67
- True Positives: 73
- False Positives: 33
- False Negatives: 27

The ROC-AUC of 0.79 indicates that the model has a reasonable ability to distinguish between the two classes across different classification thresholds.

---

🔍 Feature Interpretation

The Logistic Regression coefficients were:

Feature| Coefficient| Effect on Class 1
"backlogs"| +0.62| Strongest push toward Class 1
"attendance_pct"| +0.56| Pushes toward Class 1
"projects_completed"| +0.55| Pushes toward Class 1
"internship_months"| -0.40| Pushes toward Class 0
"cgpa"| -0.46| Pushes toward Class 0
"coding_score"| -0.52| Strongest push toward Class 0

⚠️ Important Interpretation Note

The coefficient direction raises an important question.

If Class 1 = Eligible, then the model would imply that more backlogs and lower CGPA increase the likelihood of being eligible, which is counterintuitive.

The project documentation therefore recommends confirming the exact meaning of the target labels before presenting Class 1 as "eligible."

---

🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

---

📁 Suggested Repository Structure

student-placement-eligibility-predictor/
│
├── dataset/
│   └── dataset_07_student_placement_eligibility.csv
│
├── notebooks/
│   └── student_placement_prediction.ipynb
│
├── src/
│   └── model.py
│
├── results/
│   ├── confusion_matrix.png
│   └── roc_curve.png
│
├── README.md
└── requirements.txt

---

🚀 How to Run

1. Clone the repository

git clone https://github.com/your-username/student-placement-eligibility-predictor.git
cd student-placement-eligibility-predictor

2. Install dependencies

pip install pandas numpy scikit-learn matplotlib seaborn

Or:

pip install -r requirements.txt

3. Run the project

Open the Jupyter Notebook:

jupyter notebook

Then open:

notebooks/student_placement_prediction.ipynb

---

📋 Requirements

Create a "requirements.txt" file containing:

pandas
numpy
scikit-learn
matplotlib
seaborn
jupyter

---

⚠️ Limitations

The model has several limitations:

1. Individual features have relatively weak correlations with the target.
2. The evaluation uses a single train/test split rather than cross-validation.
3. Performance may vary with a different random split.
4. The dataset appears to be a synthetic practice dataset and may not represent real-world placement decisions.
5. The model achieves 70% accuracy, so it should not be used independently for real placement decisions.
6. The exact interpretation of target class "1" needs to be confirmed.

---

🎯 Conclusion

The Logistic Regression model achieved:

70% Accuracy | 71% F1-Score | 0.79 ROC-AUC

This demonstrates a reasonable baseline for the given dataset and performs meaningfully better than the 50% random-guessing baseline expected for a balanced binary classification problem.

However, the model should be considered a machine learning project/baseline rather than a production placement decision system because of the dataset limitations and the uncertainty surrounding the target-label interpretation.

---

👨‍💻 Author

Manikanta Gattadi

B.Sc. Data Science Student

Intern ID: LD-1787381790998

Project Date: September 4, 2026

---

⭐ If you found this project useful

Feel free to star ⭐ the repository and explore the implementation.
