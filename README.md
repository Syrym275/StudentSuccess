# StudentSuccess

# Student Dropout Prediction — README

## Project Overview

This project focuses on predicting student academic outcomes using machine learning. The dataset was taken from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success?utm_source=chatgpt.com) and contains information about students’ academic performance, demographic background, and financial status.

The goal of the project was to classify students into one of three categories:

* Dropout
* Enrolled
* Graduate

This is a multi-class classification problem.

---

## Dataset Information

* Dataset size: 4,424 rows
* Features: 36 input features + 1 target column
* Missing values: None
* Target variable: `Target`

The dataset includes:

* Academic performance data
* Financial information
* Demographic details
* Economic indicators

Examples of features:

* Age at enrolment
* Admission grade
* Tuition fees up to date
* Scholarship holder
* Curricular units approved

---

## Project Hypothesis

We hypothesized that:

* Curricular units approved in the 1st semester
* Tuition fees up to date
* Age at enrolment

would be the strongest predictors of student dropout.

The idea behind this hypothesis was that early academic performance and financial stability strongly influence whether a student continues their education successfully.

---

## Technologies Used

### Programming Language

* Python

### Libraries

* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* ucimlrepo

### Machine Learning Models

* Logistic Regression
* Decision Tree
* Support Vector Machine (SVM)

---

## Project Process

### 1. Data Collection

The dataset was downloaded directly from the UCI repository using the `ucimlrepo` library.

### 2. Data Preprocessing

Several preprocessing steps were applied:

* Label encoding of categorical values
* Feature scaling using `StandardScaler`
* Train-test split (80/20)
* Stratified sampling to preserve class distribution
* Feature engineering:

  * Created a new feature called `Total Approved`

### 3. Exploratory Data Analysis (EDA)

EDA was performed to identify patterns and relationships in the data.

Main findings:

* Graduate students formed the largest class
* Older students showed a higher dropout tendency
* Higher admission grades were associated with graduation
* Academic performance features showed strong correlations

### 4. Model Training

Three machine learning models were trained and compared:

* Logistic Regression
* Decision Tree
* Support Vector Machine (SVM)

Cross-validation was also applied to evaluate model stability.

### 5. Model Evaluation

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

---

## Results

| Model               | Accuracy | F1-Score |
| ------------------- | -------- | -------- |
| Logistic Regression | 0.768    | 0.753    |
| Decision Tree       | 0.697    | 0.699    |
| SVM                 | 0.499    | 0.333    |

Logistic Regression achieved the best overall performance despite being the simplest model.

Key observations:

* The model predicted the `Graduate` class very well
* The `Enrolled` class was the hardest to classify
* Class imbalance affected model performance

---

## Error Analysis

The main challenge was predicting students in the `Enrolled` category because their characteristics overlapped with both Dropout and Graduate students.

Other important findings:

* Some dropout students were incorrectly predicted as graduates
* Class imbalance biased predictions toward the majority class
* The dataset lacked longitudinal behavioral data

---

## Future Improvements

Possible improvements include:

* Hyperparameter tuning for SVM
* Using ensemble models such as Random Forest or Gradient Boosting
* Applying SMOTE or class weighting
* Adding engagement and attendance data
* Using longitudinal semester-by-semester data

---

## Conclusion

This project demonstrated how machine learning can be used to identify students at risk of dropping out. Among the tested models, Logistic Regression produced the best results with 76.8% accuracy.

The project also highlighted the importance of:

* Feature engineering
* Proper preprocessing
* Class imbalance handling
* Model evaluation beyond simple accuracy

Overall, the project provides a practical example of applying machine learning techniques to real-world educational data analysis.
