# Breast Cancer Prediction

This project implements a machine learning pipeline to predict breast cancer diagnoses (Malignant vs Benign) using the Breast Cancer Wisconsin dataset. It includes data preprocessing, visualization, model training, evaluation, and hyperparameter tuning.

## 📁 Dataset

- **Source**: `data.csv` (Breast Cancer Wisconsin Diagnostic Data Set)
- **Instances**: 569
- **Features**: 30 numerical features describing characteristics of cell nuclei
- **Target**: `diagnosis` (M = Malignant, B = Benign)

##  Data Preprocessing

- Dropped the `Unnamed: 32` column containing all null values
- Converted categorical labels (`diagnosis`) to numerical (M → 1, B → 0)
- Selected relevant features for prediction based on correlation:
  - `radius_mean`, `perimeter_mean`, `area_mean`, `symmetry_mean`, `compactness_mean`, `concave points_mean`
- Applied `StandardScaler` for feature normalization

##  Exploratory Data Analysis

- Used `matplotlib`, `seaborn`, and `plotly` for:
  - Histograms and count plots
  - Pair plots and scatter plots
  - Correlation heatmaps

##  Models Used

Trained and compared the following classifiers:

- Logistic Regression
- Random Forest
- Decision Tree
- Support Vector Machine (SVC)
- K-Nearest Neighbors (via GridSearch)

##  Evaluation Metrics

- Accuracy Score
- Confusion Matrix
- F1 Score
- Classification Report
- Cross-Validation Scores (K-Fold = 5 or 10)
- Grid Search for hyperparameter tuning

##  Model Performance Summary

| Model                | Test Accuracy|
|----------------------|-------------|
| Logistic Regression  | ~90.9%      | 
| Random Forest        | ~92.5%      |
| Decision Tree        | ~90.9%      | 
| SVC                  | ~91.5%      | 

Hyperparameter tuning (GridSearchCV) was performed for:
- `DecisionTreeClassifier`
- `KNeighborsClassifier`
- `SVC`
- `RandomForestClassifier`

##  Requirements

- Python 3.11+
- pandas, numpy, matplotlib, seaborn, scikit-learn, plotly

Install dependencies using:
```bash
pip install -r requirements.txt