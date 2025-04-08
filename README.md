# Predicting Patient Appointment Attendance Using Machine Learning and Neural Networks

## Overview
This project aims to predict whether patients will show up for their medical appointments based on various features like patient history, demographics, and other factors. By leveraging different machine learning models and advanced neural network architectures, this project attempts to address the challenges of class imbalance and improve prediction accuracy for "No-Show" instances.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Models Implemented](#models-implemented)
- [Results and Evaluation](#results-and-evaluation)


## Dataset
The dataset consists of patient appointment records with the following features:
- **Demographic Information**: Gender, Age.
- **Health Factors**: Presence of conditions like Hypertension, Diabetes, Alcoholism, Handicap.
- **Appointment Details**: Scheduled day, appointment day, receipt of SMS reminder, and the target variable indicating whether the patient showed up for their appointment (`Showed_up`).

## Project Workflow

### 1. Data Exploration and Cleaning
- Conducted **exploratory data analysis (EDA)** to understand the distribution of categorical and numerical features.
- Identified potential issues like **class imbalance** (many more "Show-Up" instances than "No-Show"), missing values, and one-hot encoding needs for categorical features like `Neighbourhood`.

### 2. Feature Engineering
- Created new features to improve model performance, such as `missed_appointment_before`, which tracks if a patient has previously missed any appointments.
- Applied **correlation analysis** to assess the relationship between features and the target variable, dropping irrelevant columns like `PatientId` and `AppointmentID`.

### 3. Data Preprocessing
- **Standardization**: Scaled the features using `StandardScaler` to ensure that all variables are on a similar range.
- **Encoding**: Converted boolean columns (e.g., `True`/`False`) to **1/0** and applied **one-hot encoding** for categorical features like `Neighbourhood`.

### 4. Model Training and Evaluation
- **Models Trained**: A variety of machine learning models were implemented and compared:
  - **Random Forest, Support Vector Machine (SVM), XGBoost**.
  - **Neural Networks**: Designed multiple architectures, optimizing hyperparameters and using advanced techniques like dropout regularization and early stopping.

- **Evaluation Metrics**:
  - Calculated metrics such as **accuracy**, **confusion matrix**, **precision**, **recall**, **F1-score**, and **ROC-AUC** to provide a balanced evaluation of model performance, particularly for imbalanced data.
  - **Threshold Tuning**: Adjusted the classification threshold to improve sensitivity to "No-Show" instances.

## Models Implemented

1. **Baseline Neural Network Model**
   - A basic neural network was trained with moderate complexity and dropout regularization to avoid overfitting.
   - Achieved approximately **79.5% accuracy** but struggled to identify "No-Show" instances due to class imbalance.

2. **Enhanced Neural Network Model**
   - Increased the network's depth and width by adding layers with more neurons, creating a deeper architecture to learn complex data patterns.
   - Applied **aggressive dropout (60%)** and **early stopping** to balance complexity with generalizability.
   - Improved overall accuracy to **88.3%**, but faced challenges in predicting "No-Show" instances effectively.

3. **Optimization with Hyperparameter Tuning**
   - Used `RandomizedSearchCV` to find the optimal combination of hyperparameters like dropout rate, optimizer, and activation functions.
   - Implemented a stratified train-test split to ensure balanced class distribution in training and evaluation.

## Results and Evaluation
- The second neural network model showed significant improvements in predictive accuracy for the "Show-Up" class. However, due to the inherent imbalance, additional tuning (e.g., threshold adjustments, weighted loss) is necessary to improve recall for "No-Show" instances.
- The project demonstrated the importance of regularization, hyperparameter tuning, and threshold adjustments in building robust neural networks for imbalanced classification tasks.




---

### **Author**
Padraig O'Brien | [LinkedIn](https://www.linkedin.com/in/padraig-o-brien-abb460221/) | [Email](padraigobrien00@gmail.com)

Feel free to connect if you have any questions or feedback!

