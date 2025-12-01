# Heart_stroke_prediction_final
Dataset
Source: Kaggle Stroke Prediction Dataset
5,110 records, 12 features
Target: stroke (binary)
Note: Download Stroke Prediction Dataset from the Kaggle link and rename it to "stroke_data.csv" and upload it to Colab when running the notebook.

stroke_data.csv (5,110 records, 12 features)
Target: stroke (binary)
Workflow
Preprocessing

Fill missing BMI (median) and smoking status (mode)
Label encode binary features, one-hot encode multi-class features
Remove id column
Train-Test Split & Scaling

Stratified 80/20 split
StandardScaler applied to numeric features
Handle Class Imbalance
Advacned SMOTE techniques applied to training set only models

Logistic Regression, Random Forest, XGBoost, CAT BOOST
Fixed random seeds and reference hyperparameters
Evaluation, SHAP and LIME implemented, Fairness adn risk stratification is also additionally implemented

Accuracy, Precision, Recall, F1-score, ROC-AUC
Confusion matrices, ROC & Precision-Recall curves
Result

Best model selected based on Recall: CAT_SMOTEEn
How to Run in Colab
Open the notebook directly in Colab:
Open in Colab

Upload stroke_data.csv when prompted.

Run the cells sequentially, all preprocessing, training, evaluation, and cross-validation steps are included.


Full workflow is implemented in the Colab notebook
Reference
Akinwumi, P. O., Ojo, S., Nathaniel, T. I., Wanliss, J., Karunwi, O., & Sulaiman, M. (2025). Evaluating machine learning models for stroke prediction based on clinical variables. Frontiers in Neurology, 16, 1668420
