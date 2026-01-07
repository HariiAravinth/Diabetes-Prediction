# Diabetes Prediction Using Machine Learning and Tabular Transformers

## Abstract

Diabetes is a chronic metabolic disorder with significant global health implications. Early detection plays a crucial role in reducing long-term complications and healthcare costs. This project investigates the application of supervised machine learning techniques to predict the onset of diabetes using structured clinical and demographic data. Multiple classification models are developed, evaluated, and compared against tabular transformer architectures. The dissertation aims to determine the most effective predictive approach, with particular emphasis on data preprocessing, feature scaling, and model interpretability. Given the sensitive nature of healthcare applications, special attention is paid to fairness, bias, and explainability. Tabular Transformers are selected as the primary benchmark due to their strong predictive performance and built-in interpretability mechanisms, making them well-suited for high-stakes medical decision support.

---

## 1. Introduction

Diabetes mellitus represents one of the most pressing public health challenges worldwide, affecting hundreds of millions of individuals and placing a substantial burden on healthcare systems. A significant proportion of affected individuals remain undiagnosed until complications arise, highlighting the importance of early risk identification. Advances in machine learning provide opportunities to augment traditional screening methods by leveraging routinely collected clinical data to identify high-risk individuals.

This project explores the use of both conventional machine learning models and advanced deep learning architectures for diabetes prediction. While traditional models such as logistic regression and decision trees offer simplicity and interpretability, they may struggle to capture complex, non-linear interactions between risk factors. Recent developments in tabular transformers promise improved predictive performance while retaining a degree of transparency through attention-based feature selection. This dissertation evaluates whether such models offer a meaningful advantage in both accuracy and explainability.

---

## 2. Problem Statement and Hypotheses

### Problem Statement

Can diabetes be accurately and fairly predicted from structured clinical data using supervised machine learning, while maintaining transparency and interpretability suitable for healthcare deployment?

### Hypotheses

- Advanced tabular transformer models can outperform conventional machine learning approaches in predictive performance  
- Robust preprocessing and feature scaling significantly improve model reliability  
- Attention-based models provide more interpretable and trustworthy predictions compared to black-box alternatives  

---

## 3. Research Objectives

- To analyse a clinical diabetes dataset and understand key risk factors  
- To design a robust preprocessing pipeline addressing missing values and feature scaling  
- To implement and compare conventional machine learning models with tabular transformers  
- To evaluate models using appropriate performance and fairness metrics  
- To assess interpretability and explainability of predictions in a healthcare context  

---

## 4. Research Questions

1. How accurately can diabetes be predicted using structured clinical attributes?  
2. Do tabular transformers outperform traditional machine learning models?  
3. Which clinical features most strongly influence diabetes predictions?  
4. How interpretable and fair are the resulting models for use in sensitive medical settings?  

---

## 5. Dataset Description

- **Dataset:** Pima Indians Diabetes Dataset  
- **Format:** CSV  
- **Instances:** 768 records  
- **Target Variable:** Outcome (0 – Non-Diabetic, 1 – Diabetic)  
- **Class Distribution:** Approximately 35% positive cases  

### Features

- Number of Pregnancies  
- Plasma Glucose Concentration  
- Diastolic Blood Pressure  
- Triceps Skinfold Thickness  
- Serum Insulin  
- Body Mass Index (BMI)  
- Diabetes Pedigree Function  
- Age  

The dataset contains biologically implausible zero values representing missing measurements, which require careful handling to avoid bias.

---

## 6. Experimental Environment

- **Programming Language:** Python 3  
- **Core Libraries:**  
  - pandas, numpy  
  - scikit-learn  
  - matplotlib, seaborn  
- **Deep Learning Frameworks:**  
  - PyTorch  
  - TabNet  
  - RTDL  

Development and experimentation were conducted using **Google Colab**.

---

## 7. Data Preprocessing and Feature Engineering

A comprehensive preprocessing pipeline was implemented to ensure data quality and fairness:

- Identification of missing values encoded as zeros  
- Imputation of missing clinical measurements using **FairCut imputation** for more realistic data handling  
- **SMOTE** applied to mitigate class imbalance and reduce bias  
- Creation of missingness indicators where appropriate  
- Feature standardisation using **z-score normalisation**  
- Stratified train–test splitting to preserve class distribution  

These steps were essential to prevent data leakage and improve model convergence, particularly for distance-based and neural network models.

**Notebook:** `Revised_Diabetes_Prediction.ipynb`

---

## 8. Exploratory Data Analysis

Exploratory analysis was conducted to examine:

- Feature distributions and outliers  
- Correlations between clinical variables and diabetes outcome  
- Class imbalance effects  

Glucose concentration, BMI, and age emerged as strongly associated with diabetes risk, aligning with established clinical knowledge.

---

## 9. Model Development

### 9.1 Conventional Machine Learning Models

The following baseline models were implemented:

- Logistic Regression  
- K-Nearest Neighbours (KNN)  
- Decision Tree Classifier  
- Support Vector Machines (SVM)  
- Random Forest  
- XGBoost  

These models provide interpretability and establish reference performance benchmarks.

### 9.2 Tabular Transformer Models

Advanced deep learning models for tabular data were implemented as benchmarks:

- **TabNet (Attentive Deep Tabular Learner)**  

TabNet was selected due to its:

- Attention-based feature selection  
- Built-in interpretability through feature masks  
- Strong performance on structured medical datasets  

### 9.3 FT-Transformer Models

The FT-Transformer model was also implemented. Although not specifically designed for categorical-heavy use cases, it proved to be effective, demonstrating that advanced deep learning architectures can deliver reliable and interpretable predictions across a wide range of tabular scenarios.

---

## 10. Model Evaluation

Models were evaluated using metrics appropriate for imbalanced medical datasets:

- Accuracy  
- Precision, Recall, and F1-score  
- Confusion Matrix  

Particular emphasis was placed on **recall**, as false negatives represent missed diagnoses in healthcare settings.

---

## 11. Results and Discussion

- Conventional models achieved reasonable baseline performance with good interpretability  
- Feature scaling significantly improved KNN and logistic regression results  
- TabNet demonstrated superior ability to capture non-linear feature interactions  
- Attention-based explanations highlighted clinically meaningful risk factors  

The results indicate that tabular transformers provide a strong balance between predictive power and explainability.

---

## 12. Fairness and Explainability Considerations

Given the high-stakes nature of medical decision-making, fairness and transparency were treated as first-class concerns:

- Evaluation focused on reducing false negatives  
- Preprocessing strategies aimed to avoid bias introduced by missing data  
- TabNet’s feature attribution mechanisms improved trust and interpretability  

Interpretability tools such as **SHAP** and **LIME** were applied across all models. For tabular transformers, a strong alignment was observed between intrinsic attention mechanisms and SHAP-based feature attributions, reinforcing their suitability for explainable healthcare AI.

---

## 13. Conclusion

This dissertation demonstrates that diabetes prediction can be significantly enhanced using modern machine learning techniques. While conventional models provide strong baselines, tabular transformer architectures such as TabNet offer improved performance and intrinsic interpretability. With careful preprocessing and fairness-aware evaluation, such models hold promise for real-world clinical decision support.

---

## 14. Future Work

- Extend evaluation to larger and more diverse clinical datasets  
- Incorporate additional fairness metrics and bias analysis  
- Compare with other transformer-based tabular models  
- Deploy the model as an interpretable clinical decision support system  

---

## Authors

**Harii Ganesh Aravinth**  
Heriot-Watt University
