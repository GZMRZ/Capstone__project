# 🏗️ Building Risk Prediction — Machine Learning Project

## 📌 Project Overview
This project develops a **machine learning classification system** to predict building risk outcomes using structural, environmental, and contextual data.  
Because the dataset is **imbalanced**, the focus is on building a model that reliably identifies high-risk cases rather than maximizing accuracy alone.

The project follows a **real-world ML workflow**, from data cleaning and visualization to model comparison and interpretation.

---

## 🎯 Objectives
- Clean and preprocess building data
- Perform exploratory data analysis (EDA)
- Handle missing values, outliers, and class imbalance
- Train and compare multiple classification models
- Select the best model using appropriate evaluation metrics
- Interpret model behavior and results

---

## 📂 Dataset Description
The dataset contains:
- **Building Dimension features** (e.g., size, age, insured period)
- **Binary & categorical features** (e.g., painted, fenced, garden, settlement)
- **Context variables** (e.g., Geo Code, Year of Observation)
- **Target variable** indicating building risk outcome

Some variables were retained for reference but **explicitly excluded from model training** where they did not contribute predictive value.

---

## 🧹 Data Preprocessing
The following preprocessing steps were applied:

- Removed duplicate records
- Handled missing values:
  - Median imputation for numerical features
  - Logical mapping for categorical features
- Converted categorical variables to numerical form
- Treated outliers in Building Dimension features using **IQR capping**
- Retained identifier/context variables but excluded them from feature selection

---

## 📊 Exploratory Data Analysis (EDA)
EDA included:
- Distribution plots for numerical variables
- Pie charts and bar plots for categorical variables
- Correlation analysis to identify multicollinearity
- Outlier detection using boxplots
- Class distribution analysis to detect imbalance

### Key Findings
- Significant **class imbalance** was present
- Some categorical features were highly correlated
- Contextual variables showed very low correlation with the target

---

## ⚖️ Handling Class Imbalance
Due to class imbalance, the following strategies were used:

- Stratified train–test split
- Use of **class weights** during training
- Evaluation using imbalance-aware metrics:
  - Precision
  - Recall
  - F1-score
  - ROC-AUC

**Accuracy was not used as the primary evaluation metric.**

---

## 🤖 Models Trained
The following models were trained and evaluated on the same dataset split:

- Logistic Regression (baseline)
- Decision Tree
- Random Forest
- Gradient Boosting

---

## 📈 Model Evaluation Results

| Model | Precision | Recall | F1-Score | ROC-AUC |
|------|----------|--------|---------|--------|
| Logistic Regression | 0.396 | **0.564** | **0.465** | 0.693 |
| Decision Tree | 0.394 | 0.488 | 0.436 | 0.672 |
| Random Forest | 0.366 | 0.365 | 0.366 | 0.630 |
| Gradient Boosting | **0.537** | 0.245 | 0.337 | **0.694** |

---

## 🏆 Best Model Selection
**Logistic Regression** was selected as the final model because it:

- Achieved the **highest F1-score**
- Had the **best recall**, which is critical for detecting high-risk buildings
- Demonstrated stable and interpretable behavior
- Outperformed more complex models on imbalance-aware metrics

---

## 🔍 Model Interpretation
A confusion matrix was used to analyze prediction behavior:

- The model correctly identified a substantial number of high-risk buildings
- Some false positives were observed, which is acceptable in a risk-focused context
- The model significantly outperformed a naive baseline

Feature coefficients were analyzed to ensure decisions aligned with domain knowledge.

---

## 🧠 Key Takeaways
- More complex models do not always perform better
- Proper evaluation metrics matter more than raw accuracy
- Handling class imbalance is critical in risk prediction
- Model interpretability is a strength, not a limitation

---

## 🛠️ Tools & Libraries
- Python  
- pandas, numpy  
- matplotlib, seaborn  
- scikit-learn  
- imbalanced-learn  

---

## 🚀 Future Improvements
- Hyperparameter tuning for ensemble models
- Threshold optimization based on business cost
- Feature expansion with external datasets
- Model deployment and monitoring

---

## 📬 Author
**Name:** Angel Ayantola  
**GitHub:** *(https://github.com/GZMRZ)*

---



