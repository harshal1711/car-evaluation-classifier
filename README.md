# Car Evaluation Classification

This project builds and compares multiple classification models to predict car evaluation ratings using the UCI Car Evaluation dataset. The models are trained using car characteristics such as price, maintenance, and safety to predict an evaluation label: **unacceptable**, **acceptable**, **good**, or **very good**.

---

## Dataset Overview

- **Source**: [UCI Car Evaluation Dataset](https://archive.ics.uci.edu/ml/datasets/Car+Evaluation)
- **Instances**: 1,728 car records
- **Attributes**:
  - `buying`: buying price
  - `maint`: maintenance cost
  - `doors`: number of doors
  - `persons`: passenger capacity
  - `lug_boot`: luggage boot size
  - `safety`: estimated safety of the car
  - `class`: car evaluation (target variable)

All features are **ordinal categorical variables**.

---

## Project Goals

- Compare common classifiers: **Decision Tree**, **K-Nearest Neighbors**, **Logistic Regression**, **Naive Bayes**, and **SVM**
- Test models with different hyperparameters and feature encodings
- Evaluate models based on:
  - Overall accuracy
  - Per-class precision, recall, and F1-score
  - Class balance in predictions
- Assess the effect of treating ordinal features as:
  - **Categorical (One-Hot Encoding)**
  - **Ordinal numeric (Label Encoding)**

---

## Modeling Approach

- Preprocessed the dataset using both **Label Encoding** and **One-Hot Encoding**
- Applied grid/randomized search for hyperparameter tuning
- Used stratified train-test splits for balanced evaluation
- Tracked class-specific metrics to assess bias or imbalance

---

## Key Findings

- **SVM and Decision Tree** delivered the highest accuracy
- Treating features as **ordinal** (via Label Encoding) produced better results than One-Hot Encoding
- Performance was strong on major classes (`unacceptable`, `acceptable`) but weaker on rare labels (`good`, `very good`)
- Decision Tree with max depth control provided an optimal balance between accuracy and interpretability

---

## Final Model

- **Model**: Decision Tree (Depth = 5)
- **Encoding**: Label Encoding
- **Accuracy**: ~93%
- **Performance**:
  - Strong on common classes
  - Recall drop for `very good` class due to class imbalance
- **Next Steps**: Consider oversampling or class weights to improve minority class detection

---
