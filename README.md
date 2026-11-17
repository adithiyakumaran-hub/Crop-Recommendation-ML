# Crop Recommendation System using Machine Learning

## Project Overview

This project uses machine learning to recommend suitable crops based on soil nutrients and environmental conditions.

The model analyses seven input parameters — Nitrogen (N), Phosphorus (P), Potassium (K), temperature, humidity, pH, and rainfall — to predict the most suitable crop for the given conditions.

The project covers data exploration, preprocessing, model training, evaluation, feature importance, hyperparameter tuning, and crop prediction.

## Dataset

**Dataset:** Crop Recommendation Dataset  
**Source:** [Kaggle – Crop Recommendation Dataset](https://www.kaggle.com/datasets/atharvaingle/crop-recommendation-dataset)

The original dataset contains 2,200 records and 8 columns.

### Features

| Feature | Description |
|---|---|
| N | Nitrogen content in soil |
| P | Phosphorus content in soil |
| K | Potassium content in soil |
| Temperature | Temperature in the environment |
| Humidity | Relative humidity |
| pH | Soil pH value |
| Rainfall | Rainfall in the region |
| Label | Recommended crop |

## Project Workflow

### 1. Data Exploration
- Loaded and inspected the dataset.
- Checked dataset dimensions and data types.
- Checked for missing values and duplicate records.
- Analysed feature distributions and correlations.
- Studied the relationship between input features and crop labels.

### 2. Data Preprocessing
- Detected outliers using the Interquartile Range (IQR) method.
- Removed rows containing outliers.
- Reduced the dataset from 2,200 to 1,768 records.
- Encoded crop labels using Label Encoding.
- Split the dataset into training and testing sets using an 80:20 ratio.
- Applied StandardScaler to numerical features.

### 3. Model Training

The following machine learning algorithms were implemented:

- Logistic Regression
- Decision Tree Classifier
- K-Nearest Neighbors (KNN)
- Random Forest Classifier

### 4. Model Evaluation

Models were evaluated using:
- Accuracy score
- Confusion matrix
- Classification report
- 5-fold cross-validation

### 5. Feature Importance

Random Forest feature importance was used to understand the contribution of each feature to crop prediction.

The most influential features in this experiment were rainfall and humidity, while pH had the lowest feature importance.

### 6. Feature Selection

The pH feature was removed and the Decision Tree model was trained again.

- Original Decision Tree accuracy: 99.72%
- Accuracy after removing pH: 98.87%

This showed that removing pH slightly reduced model performance.

### 7. Hyperparameter Tuning

GridSearchCV was used to tune the Decision Tree Classifier.

**Best parameters:**
- Criterion: entropy
- Max depth: None
- Minimum samples per leaf: 1
- Minimum samples to split: 2

Best cross-validation accuracy: 98.44%

## Model Performance

The following results were obtained on the test dataset:

| Algorithm | Test Accuracy |
|---|---:|
| Logistic Regression | 96.05% |
| K-Nearest Neighbors | 96.61% |
| Decision Tree | **99.72%** |
| Random Forest | 99.44% |
| Tuned Decision Tree | 98.87% |

The Decision Tree Classifier achieved the highest test accuracy of **99.72%**.

Its 5-fold cross-validation results were:

- Mean accuracy: 97.67%
- Standard deviation: 0.76%

Based on these experimental results, the Decision Tree Classifier was selected as the final model.

## Sample Prediction

A sample prediction was performed using the following input values:

| Parameter | Value |
|---|---:|
| Nitrogen | 90 |
| Phosphorus | 42 |
| Potassium | 43 |
| Temperature | 21 |
| Humidity | 82 |
| pH | 6.5 |
| Rainfall | 203 |

**Predicted Crop: Rice**

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## How to Run the Project

1. Clone this repository:

   ```bash
   git clone https://github.com/adithiyakumaran-hub/Crop-Recommendation-ML.git
   ```

2. Open the project folder:

   ```bash
   cd Crop-Recommendation-ML
   ```

3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

4. Open Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `crop-recommendation.ipynb` and run the cells.

Download the dataset from the Kaggle link above and place `Crop_recommendation.csv` in the appropriate working directory before running the notebook.

## Conclusion

This project demonstrates how machine learning can be applied to agricultural data to support crop recommendation.

By analysing soil nutrient levels and environmental conditions, the implemented models were able to classify suitable crops with high accuracy on the test dataset.

The Decision Tree Classifier achieved the best test accuracy among the evaluated models.

**Note:** These results are based on the selected dataset and experimental train-test split. They should not be interpreted as a guarantee of real-world agricultural performance.

---

## Author

**Machine Learning Project – Crop Recommendation System**

