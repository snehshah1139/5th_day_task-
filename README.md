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

## **Key Takeaways**

- Data preprocessing and encoding matter as much as model selection  
- Ensemble models like Random Forest are useful for noisy or imbalanced data  
- Evaluation metrics beyond accuracy (like precision, recall) reveal the true model performance  
- Visualizations and EDA help inform better model choices

## **GRAPH VISUILZATIONS FOR WHOLE TASK

![Screenshot (67)](https://github.com/user-attachments/assets/cddbe243-e89d-4c8c-9b45-da67338c53a7)

Decision Tree Visualization - Insights
The root node splits on Credit_History, indicating it is the most important feature for predicting loan approval.
When Credit_History <= 0.5 (typically poor credit), most predictions are for loan rejection (class = No).
When Credit_History > 0.5, features like CoapplicantIncome, Loan_Amount_Term, and Property_Area influence the decision.
Branches with low Gini index (close to 0) show pure or nearly pure class distributions — high model confidence.
Applicant financial factors like ApplicantIncome and LoanAmount are important at deeper levels.
Tree depth and splits are well-controlled due to max_depth=4, helping reduce overfitting while still capturing patterns


![Screenshot (68)](https://github.com/user-attachments/assets/8ef41062-3834-4413-9f66-d8a59aaa205d)

Feature Importance Insights
Credit_History is the most important feature, contributing the most to loan approval predictions.
ApplicantIncome and LoanAmount are also strong predictors, indicating financial capability is a major factor.
CoapplicantIncome plays a moderate role, especially in cases with joint applications.
Loan_Amount_Term, Property_Area, and Dependents contribute to a lesser extent.
Features like Married, Gender, Education, and Self_Employed have very low importance.
These may not influence approval decisions significantly or may have been captured indirectly by other features.
Focus for model tuning can be placed on top features to optimize performance and reduce noise.


![Screenshot (69)](https://github.com/user-attachments/assets/c5c07c16-9ed2-45f6-9e74-166b34aeb390)

Cross-Validation Score Comparison insights
Cross-validation is used to check how well our model performs on different parts of the dataset.
It helps us make sure the model is not just doing well on one test set but performs consistently overall.
Average Accuracy Scores from 5-Fold Cross-Validation:
Decision Tree Average Score: 0.7997 (≈ 80%)
Random Forest Average Score: 0.7883 (≈ 79%)
Insight:
The Decision Tree model performed slightly better than the Random Forest model in cross-validation.
This means the Decision Tree gave more consistent results across multiple parts of the dataset.
Even though Random Forest is generally more powerful, in this case, the simpler Decision Tree worked just as well or even a bit better.
✅ Conclusion: The Decision Tree is currently the better model for this loan approval prediction task based on average cross-validation accuracy.

---
