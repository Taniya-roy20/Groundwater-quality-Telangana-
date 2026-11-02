# Groundwater Quality Classification Using Machine Learning

### Irrigation Suitability Assessment of Groundwater in Telangana, India (2018–2020)

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Classification-orange)
![Project](https://img.shields.io/badge/Project-Academic%20Research-green)

---

## 📌 Overview

This research project investigates the application of classical machine-learning models for groundwater quality classification in Telangana, India. The study uses post-monsoon groundwater records collected from 33 districts during 2018–2020 to assess groundwater suitability for irrigation.

Two classification tasks are considered:

1. **Residual Sodium Carbonate (RSC) Classification** — classifying groundwater into P.S. (Suitable), MR (Marginally Suitable), and U.S. (Unsuitable) categories.
2. **USSL Irrigation Classification** — classifying groundwater into irrigation suitability classes based on salinity and sodium hazard.

The project evaluates multiple classical machine-learning algorithms using a grouped cross-validation strategy.

## 🎯 Research Objectives

- Analyze groundwater chemical characteristics relevant to irrigation suitability.
- Develop machine-learning models for RSC and USSL classification.
- Compare the performance of classical classification algorithms.
- Investigate the influence of groundwater chemical features on model predictions.
- Identify challenges associated with imbalanced groundwater quality classes.
- Evaluate the limitations of threshold-based classification and model generalization.

## 📊 Dataset

| Property | Description |
|---|---|
| Study area | Telangana, India |
| Time period | 2018–2020 |
| Sampling period | Post-monsoon |
| Number of records | 1,106 |
| Geographic coverage | 33 districts |
| Chemical features | 16 |
| Prediction tasks | RSC and USSL classification |

The dataset contains groundwater chemical measurements used to determine irrigation suitability.

**Dataset source:** [Add original dataset source URL here]

## 🧪 Methodology

The project follows the workflow below:

1. **Data Loading** — importing and examining groundwater records.
2. **Data Preprocessing** — handling missing values and preparing chemical features.
3. **Target Classification** — preparing RSC and USSL target labels.
4. **Model Development** — training classical machine-learning classifiers.
5. **Model Evaluation** — evaluating models using grouped cross-validation.
6. **Visualization** — generating confusion matrices, correlation analysis, and feature-importance plots.
7. **Interpretation** — analyzing model performance, class imbalance, and limitations.

### Cross-Validation Strategy

A grouped 5-fold StratifiedGroupKFold strategy was used. Identical chemical profiles were kept within the same fold to reduce the possibility of identical records appearing in both training and validation sets.

Preprocessing was performed through pipelines to help prevent data leakage.

## 🤖 Machine-Learning Models

The following classical machine-learning models were evaluated for RSC classification:

- Logistic Regression
- Gaussian Naive Bayes
- Support Vector Machine (SVM)
- K-Nearest Neighbors (KNN)
- Decision Tree Classifier

An SVM classifier was also evaluated for the 13-class USSL irrigation classification task.

## 📈 Key Results

### RSC Classification

The RSC dataset contains three classes:

| Class | Records | Percentage |
|---|---:|---:|
| P.S. | 982 | 88.8% |
| U.S. | 75 | 6.8% |
| MR | 49 | 4.4% |

| Model | Accuracy | Macro-F1 |
|---|---:|---:|
| Decision Tree | 0.9991 | 0.9954 |
| Logistic Regression | 0.9322 | 0.7987 |
| Gaussian Naive Bayes | 0.8987 | 0.7158 |
| SVM | 0.8970 | 0.7144 |
| KNN | 0.9285 | 0.6070 |

The Decision Tree achieved very high performance because the RSC labels directly correspond to threshold-based rules involving the RSC feature. Therefore, this result primarily demonstrates the recovery of classification rules rather than independent predictive capability.

### USSL Classification

The SVM classifier achieved:

| Metric | Score |
|---|---:|
| Accuracy | 0.9024 |
| Macro-F1 | 0.4422 |

The difference between accuracy and macro-F1 reflects the imbalance among the 13 USSL classes. TDS and SAR were among the most influential features.

## 📊 Visualizations

The project includes the following visualizations:

- Feature-class correlation heatmap
- Grouped cross-validation confusion matrices for RSC models
- USSL confusion matrix
- Class-wise recall for USSL classification
- Permutation feature importance across grouped folds

### Figure 1: Feature-Class Correlation Heatmap

![Feature-Class Correlation Heatmap](figures/figure_1_correlation_heatmap.png)

### Figure 2: RSC Model Confusion Matrices

![RSC Model Confusion Matrices](figures/figure_2_rsc_confusion_matrices.png)

### Figure 3: USSL Confusion Matrix and Class-wise Recall

![USSL Classification Results](figures/figure_3_ussl_confusion_matrix.png)

### Figure 4: Permutation Feature Importance

![Permutation Feature Importance](figures/figure_4_feature_importance.png)

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## 🚀 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/Groundwater-Quality-ML-Research.git
