# Enzyme Classification  

This project applies machine learning to classify enzyme activity (**EC1** and **EC2** classes) using biochemical and molecular descriptors. The objective is to predict whether an enzyme–substrate pair belongs to class **0** (no interaction) or **1** (interaction).  

---

## Datasets  
- **train.csv** – Training data with molecular features and the target columns:  
  - **EC1** (0 = no interaction, 1 = interaction)  
  - **EC2** (0 = no interaction, 1 = interaction)  

- **test.csv** – Test data containing molecular features only (without targets). Predictions for EC1 and EC2 to be generated.   

### Class Distribution  

- **Before SMOTE:**  
  - EC1 → (1: 7916, 0: 3954)  
  - EC2 → (1: 9455, 0: 2415)  

- **After SMOTE (Balanced):**  
  - EC1 → (1: 7916, 0: 7916)  
  - EC2 → (1: 9455, 0: 9455)  

---

##  Key Features  

Each record includes biochemical descriptors used as input for classification, such as:  

- Molecular weight  
- Polarity  
- Charge-related properties  
- Other structural/chemical features  

(Target column: **EC1** or **EC2**, depending on the dataset).  

---

## ⚙️ Steps Performed  

1. **Data Loading** – Imported the datasets (`ec1.csv`, `ec2.csv`).  
2. **Data Preprocessing** –  
   - Handled missing values.  
   - Scaled numerical features.  
   - Balanced classes using **SMOTE**.  
3. **Modeling** – Trained multiple models for classification.  
4. **Evaluation** – Compared models based on **accuracy, precision, recall, and F1-score**.  
5. **Results Analysis** – Assessed performance before and after SMOTE.  

---

##  Models Tested  

- Logistic Regression  
- Random Forest Classifier  
- XGBoost Classifier  

 **Best performing model (after SMOTE):**  
- **Random Forest** → Balanced precision/recall with higher robustness across EC1 and EC2 datasets.  

---

## Results & Insights  

- Before SMOTE, models were biased toward the majority class (EC1 & EC2 = 1).  
- After applying SMOTE, models improved in identifying the minority class (0).  
- Logistic Regression improved recall for class 0 but lost some overall accuracy.  
- Random Forest provided the **best trade-off**, especially after balancing.  
- XGBoost also performed well, though slightly less balanced compared to Random Forest.  

---

 This project highlights how handling **class imbalance** with SMOTE improves model performance and fairness, ensuring better predictions for minority enzyme classes.  
