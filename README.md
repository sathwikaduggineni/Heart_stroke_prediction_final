**Heart_Stroke_Risk_Prediction_with_explainable_ML**
This project predicts the likelihood of stroke occurrence based on clinical, demographic, and lifestyle features. It implements a complete end-to-end machine learning pipeline inside a single notebook

## Dataset

- Source: [Kaggle Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)  
- 5,110 records, 12 features  
- Target: `stroke` (binary)  

> **Note:** Download `Stroke Prediction Dataset` from the Kaggle link and rename it to "stroke_data.csv" and upload it to Colab when running the notebook.


- `stroke_data.csv` (5,110 records, 12 features)  
- Target: `stroke` (binary)

**workflow**
-1.Preprocessing
-2.Train-Test Spliting & Scaling
-3.Handling dataset imbalance using advanced SMOTE techniques, 
-4.Training multiple ML models
-5.Evaluating performance
-6.comparing results
-7.SHAP & LIME Explainability
-8.Fairness Estimation
-9.Risk Stratification

1. **Preprocessing**

-Filled missing BMI using median
-Filled missing smoking status using mode
-Applied label encoding for binary categorical features
-Removed the id column

2.**Train-Test Split & Scaling**

Stratified 80/20 split
StandardScaler applied to numeric features

3. **Resampling**
Handle Class Imbalance using advanced SMOTE techiques
Implemented advanced SMOTE variants (e.g., SMOTENC / SMOTETomek / SMOTEENN depending on data structure) to training set only models
Oversampling applied only to the training set to avoid data leakage

4.**Model Training**
Logistic Regression, Random Forest, XGBoost, CAT BOOST, LightGBM
Hybrid implementation of CAT
Fixed random seeds and reference hyperparameters

5.**Evaluation**

The notebook includes comprehensive evaluation and interpretability
Model Performance Metrics
Accuracy
Precision
Recall
mcc
balanced_accuracy
f2
specivicity
F1-Score
ROC-AUC
Confusion Matrices
ROC Curves
Precision-Recall Curves

6.**Result**

Best model selected based on Recall, f2, mcc and balanced_accuracy: CAT_SMOTEEn( CatBoost trained on SMOTE-enhanced dataset)

7. **SHAP & LIME Explainability**
  - SHAP and LIME were used to explain the model’s predictions.
  - SHAP shows how each feature contributes to overall and individual predictions.
  - LIME explains single predictions by highlighting the most influential features.
   
8.**Fairness estimation**
-Fairness was evaluated by calculating group-wise performance for gender, residence type, and age groups.
-For each subgroup, the model's Recall (TPR), Selection Rate, and sample count were computed to check whether predictions were balanced and consistent across different demographic categories.

9. **Risk Stratification**
Risk levels were created using the model’s predicted probabilities

Low Risk: 0–0.30
Medium Risk: 0.30–0.70
High Risk: 0.70–1.0

Each category was summarized by total samples, true strokes, and stroke rate.
If SHAP values were available, a second stratification used total SHAP impact, split into low/medium/high based on percentile thresholds.
   
**How to Run in Colab**

1. Open the notebook directly in Colab:  
   [Open in Colab](https://colab.research.google.com/drive/11OogiBPkXzykaqr-HMjpR11MY3vIMf71#scrollTo=44Vfawwe4ZdA)

2. Upload `stroke_data.csv` when prompted.  

3. Run the cells sequentially, all preprocessing, training, evaluation metrics, results SHAP & LIME, Fairness and Risk Stratification steps are included.

**Reference**
Akinwumi, P. O., Ojo, S., Nathaniel, T. I., Wanliss, J., Karunwi, O., & Sulaiman, M. (2025). Evaluating machine learning models for stroke prediction based on clinical variables. Frontiers in Neurology, 16, 1668420
