# Kathmandu House Price Prediction

This project aims to predict house prices in Kathmandu, Nepal, using a dataset obtained from Kaggle. The project involves extensive data cleaning, feature engineering, and model building using machine learning algorithms. GridSearchCV was used to find the best model and parameters, resulting in improved prediction accuracy.

## Dataset

The dataset for this project can be found on Kaggle: [Nepali Housing Price Dataset](https://www.kaggle.com/datasets/sagyamthapa/nepali-housing-price-dataset).

### Files
- `Data_Cleaning_and_Preprocessing.ipynb`: Contains the steps for data cleaning and preprocessing.
- `ModelBuilding_and_Evaluation.ipynb`: Focuses on model building, hyperparameter tuning using GridSearchCV, and evaluating model performance.

---

## 1. Data Cleaning and Preprocessing

In the data cleaning and preprocessing phase, the following steps were taken:

1. **Handling Missing Values:**
   - Columns with a high percentage of missing values were removed.
   - Missing values in numerical columns were replaced with the median value.

2. **Outlier Detection and Removal:**
   - Outliers in numerical columns were identified and removed based on certain thresholds.

3. **Feature Engineering:**
   - Date columns were converted to a more useful format (e.g., extracting year information).
   - Categorical columns were one-hot encoded.
   - Some features, like house area and location, were normalized for better model performance.

4. **Data Splitting:**
   - The cleaned dataset was split into training and testing sets with an 80/20 ratio.

---

## 2. Model Building and Evaluation

Several regression models were trained and evaluated on the cleaned dataset. The best-performing model was selected using **GridSearchCV**, which helps in optimizing hyperparameters.

1. **Model Selection:**
   - A **DecisionTreeRegressor** was used as the primary model.
   - The hyperparameters tuned included:
     - `criterion`: Absolute Error or Mean Squared Error
     - `max_depth`: Depth of the tree
     - `min_samples_split` and `min_samples_leaf`: Minimum samples for splitting and leaf nodes

2. **Hyperparameter Tuning with GridSearchCV:**
   - GridSearchCV was run with 5-fold cross-validation, testing a total of 972 parameter combinations.
   - The best hyperparameters found were:
     ```python
     {'criterion': 'absolute_error',
      'max_depth': 10,
      'max_features': 'sqrt',
      'min_samples_leaf': 4,
      'min_samples_split': 10}
     ```

3. **Model Performance:**
     - **R² score on the test set:** 0.686

---

## Conclusion

This project demonstrates the use of data preprocessing techniques and hyperparameter tuning to improve the accuracy of house price predictions. The combination of feature engineering and GridSearchCV helped achieve an improved R² score of 0.686.

---

## Requirements

- Python 3.x
- pandas
- scikit-learn
- numpy
- matplotlib
- seaborn
