
## 🛍️ Delivery Delay Prediction & Customer Satisfaction Enhancement

This project applies machine learning to predict delivery delays in e-commerce and explores how these predictions can improve customer satisfaction. Using the Olist dataset from Brazil, five ML models are compared with a focus on both predictive performance and business actionability. The study also proposes an integrated fulfilment workflow that embeds predictive insights into customer service and logistics operations.

---

## 📌 Problem Statement

Delivery delays are a key driver of dissatisfaction in e-commerce. Yet, many platforms—including Olist—lack predictive tools to flag at-risk orders in advance. This project addresses that gap by:

* Predicting which orders are likely to be delayed
* Comparing five ML models: Logistic Regression, Random Forest, XGBoost, LSTM, and KNN
* Using SHAP for feature interpretation
* Translating predictions into operational improvements that reduce complaints and improve review scores

---

## 🧠 Technical Highlights

* **Models**: Logistic Regression (baseline), Random Forest (best performance), XGBoost (best interpretability), LSTM, and KNN
* **Evaluation Metrics**: F1 score, ROC-AUC, accuracy
  ✳️ *F1 and AUC were prioritised due to class imbalance (92% on-time vs 8% delayed orders)*
* **Model Evaluation**:
  All models were trained using 5-fold cross-validation on the training set.
  The test set (20%) was held out and only used for final evaluation to ensure generalisation validity.
* **Best Model**: Random Forest (AUC = 0.846, F1 = 0.422)
* **Interpretability**: SHAP values reveal key drivers such as `promised_shipping_days`, `freight_value`, and `customer_state`
* **Business Mechanism**: Predictive signals support proactive customer communication and dispatch prioritisation

---

## ⚖️ Class Imbalance Handling

The dataset is highly imbalanced, with delayed orders representing only 8% of the total. To mitigate this:

* Evaluation focused on **F1 score** and **AUC**, which better reflect minority class performance than accuracy
* While resampling techniques such as SMOTE were considered, they were not implemented in this version.
  Instead, the project prioritised transparency and stability through careful metric selection and cross-validation
* Further versions may explore SMOTE within cross-validation pipelines to further enhance recall

---

## 📁 Dataset

Public dataset from Kaggle – Olist Brazilian E-commerce, including:

* Order, customer, seller, product, and review data
* Geolocation and delivery timestamps
* \~96,000 transactions after merging

---

## 📊 Methodology Overview

The notebook implements a seven-step pipeline:

1. Business Problem Definition
2. Data Loading and Merging
3. Cleaning and Preprocessing (missing values, imputation, encoding)
4. Feature Engineering (shipping gaps, product volume, payment types)
5. Model Training (5 models + 5-fold cross-validation)
6. Model Evaluation (AUC, F1, SHAP analysis)
7. Business Interpretation & Recommendations

---

## 🔍 Key Results

| Model               | AUC   | F1 Score | Accuracy |
| ------------------- | ----- | -------- | -------- |
| Random Forest       | 0.846 | 0.422    | 93.8%    |
| XGBoost             | 0.836 | 0.322    | 92.9%    |
| LSTM                | 0.820 | 0.293    | 92.3%    |
| Logistic Regression | 0.810 | 0.196    | 92.3%    |
| KNN                 | 0.747 | 0.311    | 92.1%    |

---

## 💡 Business Impact

* 📉 Estimated reduction in dissatisfaction-related complaints: **up to 42%**
* ⭐ Estimated uplift in overall review score: **+0.08 points**
* 🔄 Predictive model embedded into fulfilment and customer service operations

### Suggested use cases:

* Early customer notifications for high-risk orders
* Dynamic rerouting or resource allocation
* Loyalty incentives based on predicted delay risk

---

## 🔬 Tools Used

* Python 3.9
* scikit-learn, XGBoost, SHAP
* pandas, numpy, seaborn, matplotlib
* tensorflow\.keras (for LSTM model)
* Jupyter / Google Colab

---

## 🧾 Project Structure

* Project Overview
* Data Loading and Merging
* Data Cleaning and Preprocessing
* Exploratory Data Analysis (EDA)
* Final Feature Selection
* Model Development and Evaluation

  * Logistic Regression
  * Random Forest
  * XGBoost + SHAP
  * LSTM
  * KNN
* Comparative Results
* Business Interpretation and Impact
* Conclusion and Recommendations

---

## 🚀 How to Run

1. Clone this repo
2. Download Olist dataset from Kaggle
3. Place data files in `./data/` directory
4. Open and run `deliver_delay_prediction_v1.ipynb` in Colab or Jupyter
5. Explore outputs, visualizations, and insights


---

## 📬 Author

**Frida **  
MSc Business Analytics, Queen Mary University of London  


---

## 📎 References

Key references include:  
- Capgemini (2019), Mangiaracina et al. (2019), Ravula (2022), Rezki & Mansouri (2024), Rokoss et al. (2024), Silverman (2023)
