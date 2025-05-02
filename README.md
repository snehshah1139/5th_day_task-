# 5th_day_task-
# **Task 5: Decision Tree and Random Forest Classifier**

**Internship Project – Loan Approval Prediction**  
**Objective:** Predict loan approval using applicant information via classification models.

---

## **Overview**

- **Dataset Size:** 614 records  
- **Features:** 12 input features + 1 target variable (`Loan_Status`)  
- **Goal:** Classify whether a loan application will be approved (`Y`) or not (`N`)

---

## **Step 1: Data Cleaning**

- Renamed unclear columns for better readability  
- Handled missing values using **mode imputation**  
- Converted target labels: **`Y → 1`, `N → 0`**  
- Applied **Label Encoding** to categorical features

> Dataset is now clean and ready for model building

---

## **Step 2: Exploratory Data Analysis (EDA)**

- Class distribution in `Loan_Status` is **imbalanced**  
  - Approved (1): ~420  
  - Not Approved (0): ~190  
- Visual plots helped understand the influence of features like `Credit_History`, `Education`, and `Income`

> Important Insight: Imbalance may affect model performance and needs consideration.

---

## **Step 3: Decision Tree Classifier**

- Trained a Decision Tree with controlled depth (`max_depth=4`)  
- **Accuracy:** ~77%  
- Performs well for approved loans but less precise on not approved cases

> Precision for class 0 (Not Approved) was low → model biased toward majority class

---

## **Step 4: Random Forest Classifier**

- Used ensemble of 100 trees  
- **Accuracy:** ~76%  
- Improved generalization but still reflects class imbalance

> Model is robust but still favors class 1 (Approved)

---

## **Step 5: Cross-Validation (5-Fold)**

| Model            | Mean CV Accuracy |
|------------------|------------------|
| Decision Tree    | 79.97%           |
| Random Forest    | 78.82%           |

> Slight edge for Decision Tree in cross-validation, but Random Forest offers better generalization in some test cases

---

## **Final Analysis**

- **Both models** deliver moderate accuracy (around 76–78%)  
- **Random Forest** provides better balance, but **Decision Tree** is simpler and easier to interpret  
- **Class imbalance** affects performance → future improvement with oversampling or class weighting  
- Clean data preprocessing and label encoding are critical to model performance  
- Further improvement possible using GridSearchCV, SMOTE, or ensemble tuning

---

## **
Key Takeaways**

- Data preprocessing and encoding matter as much as model selection  
- Ensemble models like Random Forest are useful for noisy or imbalanced data  
- Evaluation metrics beyond accuracy (like precision, recall) reveal the true model performance  
- Visualizations and EDA help inform better model choices

---
