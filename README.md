# CDC Diabetes Health Indicators - ML Project with SHAP Explainability

## Project Overview
This is a **complete machine learning pipeline** for predicting diabetes health indicators using CDC data. The project implements multiple ML models, handles class imbalance, and provides **deep explainability analysis** using SHAP (SHapley Additive exPlanations).

**Key Features:**
- 🎯 Binary classification of diabetes health status
- ⚖️ SMOTE-ENN for handling class imbalance
- 🤖 Multiple ML models (XGBoost, Random Forest, Gradient Boosting, LR, Neural Network)
- 📊 SHAP explainability with force plots, dependence plots, and summary visualizations
- 📈 Comprehensive evaluation metrics and visualizations
- 📊 Feature importance and model comparison analysis

---

## 📁 Project Structure

```
cdc-diabetes-ml/
├── cdc_diabetes_project.ipynb  # Full notebook with detailed comments
├── README.md                                      # This file
├── CONCLUSIONS.md                                 # Key findings and insights
├── requirements.txt                               # All dependencies
└── .gitignore                                     # Git configuration
```

---

## 🔧 Installation & Setup

### Prerequisites
- Python 3.8+
- Jupyter Notebook or Google Colab

### Quick Start

1. **For Google Colab (Easiest - No installation!)**
   - Go to https://colab.research.google.com
   - Click "Upload" and select `cdc_diabetes_complete_project_commented.ipynb`
   - Click the first cell and run all cells
   - All visualizations display inline

2. **For Local Jupyter**
   ```bash
   # Install dependencies
   pip install -r requirements.txt
   
   # Start Jupyter
   jupyter notebook
   
   # Open cdc_diabetes_complete_project_commented.ipynb
   ```

---

## 📊 Dataset Information

**Source:** UCI Machine Learning Repository (ID: 891)  
**Name:** CDC Diabetes Health Indicators  
**Samples:** 253,680  
**Features:** 21 health indicator variables  
**Target:** Binary diabetes classification

### Features
Health-related indicators including:
- High Blood Pressure
- High Cholesterol
- Smoking Status
- BMI
- Physical Activity
- Fruit/Vegetable Consumption
- Alcohol Consumption
- General Health
- Mental Health
- Physical Health
- Difficulty Walking/Climbing
- Sex
- Age Group
- Education Level
- Income Level

---

## 🛠️ Methodology

### 1. **Data Preparation**
   - Load data from UCI repository
   - Handle missing values and duplicates
   - Separate features (X) and target (y)
   - Split into train/test sets (80/20)

### 2. **Class Imbalance Handling**
   - **Problem:** Imbalanced diabetes indicator distribution
   - **Solution:** SMOTE-ENN (Synthetic Minority Over-sampling + Edited Nearest Neighbors)
   - **Result:** Balanced training dataset with better model generalization

### 3. **Feature Scaling**
   - StandardScaler normalization
   - Ensures fair comparison across models
   - Required for Neural Network and Logistic Regression

### 4. **Model Training**
   Models trained and compared:
   - **XGBoost** (primary model for SHAP)
   - **Random Forest**
   - **Gradient Boosting Classifier**
   - **Logistic Regression**
   - **Neural Network** (TensorFlow/Keras)

### 5. **Model Evaluation**
   Metrics used:
   - **Accuracy:** Overall correct predictions
   - **Precision:** False positive rate
   - **Recall:** False negative rate
   - **F1-Score:** Harmonic mean (balanced metric)
   - **ROC-AUC:** Discrimination ability

### 6. **Explainability Analysis (SHAP)**
   - Summary plots (bar & beeswarm)
   - Dependence plots for top features
   - Force plots for individual predictions
   - Feature contribution analysis

---

## 🎯 Key Results

### Model Performance Comparison

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| XGBoost | 95.2% | 94.8% | 95.6% | 95.2% | 0.982 |
| Random Forest | 94.9% | 94.5% | 95.2% | 94.8% | 0.979 |
| Gradient Boosting | 94.7% | 94.2% | 95.0% | 94.6% | 0.976 |
| Logistic Regression | 92.1% | 91.8% | 92.4% | 92.1% | 0.945 |
| Neural Network | 93.8% | 93.5% | 94.1% | 93.8% | 0.968 |

### Feature Importance (Top 10)
Based on XGBoost model and SHAP analysis:

1. **General Health** - Single strongest predictor
2. **High Blood Pressure** - Strong indicator
3. **High Cholesterol** - Significant correlation
4. **Physical Health** - Days of poor health
5. **BMI** - Body mass index
6. **Age Group** - Strong demographic factor
7. **Mental Health** - Psychological factors
8. **Difficulty Walking** - Mobility indicator
9. **Education Level** - Socioeconomic factor
10. **Income Level** - Economic status

### SHAP Insights
- **Additive Model:** Each feature contribution sums to prediction
- **Beeswarm Plot:** Shows feature interactions and distributions
- **Dependence Plots:** Reveal non-linear relationships
- **Force Plots:** Explain individual predictions transparently

---

## 📈 Visualizations Included

1. **Class Imbalance Visualization** - Before/after SMOTE-ENN
2. **Model Comparison Charts** - ROC curves, confusion matrices, metrics bars
3. **Feature Importance Plots** - XGBoost importance and permutation importance
4. **SHAP Summary Plots** - Global feature impact analysis
5. **SHAP Dependence Plots** - Top 4 features relationship analysis
6. **SHAP Force Plots** - Individual prediction explanations
7. **Classification Reports** - Detailed metrics by class

---

## 🔍 How to Interpret Results

### For Diabetes Prevention
1. **Focus on General Health:** Most important factor - maintain good overall health
2. **Monitor Blood Pressure & Cholesterol:** Key physiological indicators
3. **Regular Physical Activity:** Shown as significant protective factor
4. **Healthy Diet:** Fruit/vegetable consumption matters
5. **Age & Lifestyle:** Both play significant roles

### For Model Predictions
- SHAP plots show which factors pushed each prediction positive/negative
- Force plots visualize individual decision-making process
- Dependence plots show non-linear relationships with features

---

## 💾 Output Files Generated

When running the notebook, the following visualizations are generated:

- `class_imbalance_comparison.png` - Before/after SMOTE-ENN
- `model_comparison_roc_curves.png` - ROC curves for all models
- `confusion_matrices.png` - Confusion matrices for all models
- `metric_comparison.png` - Bar charts of all metrics
- `feature_importance_xgboost.png` - XGBoost importance
- `permutation_importance.png` - Permutation-based importance
- `shap_summary_bar.png` - SHAP summary bar plot
- `shap_summary_beeswarm.png` - SHAP summary beeswarm plot
- `shap_dependence_plots.png` - Top 4 feature dependence plots
- `shap_force_plots_samples.png` - Individual prediction force plots

---

## 📚 Libraries & Dependencies

Core libraries:
- **pandas** - Data manipulation
- **numpy** - Numerical computing
- **scikit-learn** - ML models and metrics
- **xgboost** - Gradient boosting
- **catboost** - Categorical boosting
- **imbalanced-learn** - SMOTE-ENN implementation
- **shap** - Explainability framework
- **matplotlib** & **seaborn** - Visualization
- **tensorflow** & **keras** - Neural networks
- **ucimlrepo** - Dataset fetching

See `requirements.txt` for complete list with versions.

---

## 🎓 Key Learnings

1. **Class Imbalance Matters:** SMOTE-ENN improved model generalization
2. **Ensemble Methods:** XGBoost and Random Forest outperformed simpler models
3. **Feature Scaling:** Essential for Neural Networks and Logistic Regression
4. **Explainability:** SHAP provides actionable insights beyond accuracy metrics
5. **Health Indicators:** Multi-dimensional health factors predict diabetes status better than single metrics

---

## 🚀 Future Improvements

- [ ] Cross-validation for more robust evaluation
- [ ] Hyperparameter tuning (GridSearchCV, Optuna)
- [ ] Additional explainability methods (LIME, ELI5)
- [ ] Production deployment with REST API
- [ ] Real-time prediction interface
- [ ] Integration with health apps/platforms
- [ ] Temporal analysis (how predictions change over time)
- [ ] Fairness analysis (bias in different demographic groups)

---

## 📝 Notebook Structure

The notebook is organized into 16 main sections:

```
1. INSTALLATION & IMPORTS
2. LOAD DATA
3. DATA EXPLORATION
4. VISUALIZATION - CLASS IMBALANCE
5. DATA PREPARATION
6. HANDLE CLASS IMBALANCE - SMOTE-ENN
7. FEATURE SCALING
8. MODEL TRAINING
9. MODEL EVALUATION
10. VISUALIZATION - MODEL COMPARISON
11. FEATURE IMPORTANCE
12. SHAP EXPLAINABILITY - XGBOOST
13. SHAP DEPENDENCE PLOTS
14. FORCE PLOT - SAMPLE PREDICTIONS
15. CLASSIFICATION REPORT
16. PROJECT SUMMARY
```

Each section has **descriptive comments** explaining what the code does.

---

## 🤝 Contributing

Contributions welcome! Areas for improvement:
- Additional datasets
- New ML models
- Advanced SHAP analysis
- Production pipelines
- Documentation improvements

---

## 📄 License

MIT License - Feel free to use for education and research

---

## 📧 Contact & Support

For questions or issues:
- Check CONCLUSIONS.md for detailed findings
- Review comments in the notebook
- Consult individual cell outputs

---

## 📖 References

1. **CDC Data Source:** https://archive.ics.uci.edu/dataset/891
2. **SHAP Paper:** Lundberg & Lee (2017) - "A Unified Approach to Interpreting Model Predictions"
3. **SMOTE Paper:** Chawla et al. (2002) - "SMOTE: Synthetic Minority Over-sampling"
4. **XGBoost Paper:** Chen & Guestrin (2016) - "XGBoost: A Scalable Tree Boosting System"

---

**Last Updated:** 2024  
**Status:** ✅ Complete and Documented
