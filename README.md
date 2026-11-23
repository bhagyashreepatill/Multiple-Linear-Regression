# Activity 1: Multiple Linear Regression – California Housing Dataset

**Subject:** Regression Foundations & Linear Regression  
**Activity:** Activity 1 – Multiple Linear Regression  
**Student:** Bhagyashree Patil  
**Roll Number:** AD3263

**Course:** B.Tech – Artificial Intelligence and Data Science

## 1. Objective

To predict a continuous numerical target using multiple input features, calculate a small two-feature regression model manually, verify it using Scikit-learn, compare single-feature and multiple-feature models, interpret coefficients, check residuals and multicollinearity, evaluate model performance, and predict a new example.

## 2. Dataset

- **Dataset name:** California Housing Dataset
- **Source:** [Scikit-learn – California Housing Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html)
- **Number of rows:** 20,640
- **Number of columns:** 9 (8 input features and 1 target)
- **Target:** `MedHouseVal` – median house value, expressed in units of $100,000.

### Input features

`MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, and `Longitude`.

These features describe income, housing characteristics, population/occupancy, and geographical location. They may be associated with house values, but correlation does not prove causation.

## 3. Tools and Libraries

- Python
- Jupyter Notebook / Google Colab
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Statsmodels

## 4. Work Completed

1. Loaded and inspected the California Housing Dataset.
2. Checked data types, summary statistics, missing values and duplicate records.
3. Created scatter plots and a correlation heatmap.
4. Performed manual multiple regression calculations using six observations and two features (`MedInc` and `HouseAge`).
5. Verified the manual coefficients using Scikit-learn.
6. Split the data into 80% training and 20% testing sets.
7. Trained a single-feature Linear Regression model and a multiple-feature Linear Regression model.
8. Interpreted the fitted coefficients and calculated standardised coefficients.
9. Compared test predictions and regression evaluation metrics.
10. Analysed residuals, checked multicollinearity using correlation and VIF, and predicted a new example.

## 5. Dataset Cleaning

- Missing values found: 0
- Duplicate rows found: 0
- Rows before cleaning: 20,640
- Rows after cleaning: 20,640

No rows needed to be removed.

## 6. Model Evaluation Results

Both models were evaluated on the same test set of 4,128 observations.

| Metric | Single-feature model (`MedInc`) | Multiple-feature model |
|---|---:|---:|
| MAE | 0.629909 | **0.533200** |
| MSE | 0.709116 | **0.555892** |
| RMSE | 0.842090 | **0.745581** |
| R² | 0.458859 | **0.575788** |
| Adjusted R² | 0.458728 | **0.574964** |

The multiple-feature model performed better on this test split: it had lower MAE, MSE and RMSE, and higher R² and adjusted R².

## 7. Multicollinearity Check

The VIF check identified comparatively high values for some features:

| Feature | VIF |
|---|---:|
| Latitude | 9.206 |
| Longitude | 8.876 |
| AveRooms | 7.917 |
| AveBedrms | 6.609 |

The feature correlation matrix also showed a strong relationship between `Latitude` and `Longitude` (approximately -0.925), and between `AveRooms` and `AveBedrms` (approximately 0.848). These results indicate possible multicollinearity and should be considered when interpreting individual coefficients.

## 8. New Prediction

A new example was created using the median value of each training feature.

- Predicted `MedHouseVal`: approximately 2.0300
- Target unit: $100,000
- Approximate predicted value: **$203,002.36**

This is a model estimate, not a guaranteed market sale price.

## 9. Conclusion

In this activity, Multiple Linear Regression was implemented using the California Housing Dataset to predict median house values from multiple numerical features. Data inspection, visualisation, manual matrix calculations, model training, coefficient interpretation, evaluation metrics, residual analysis and VIF checks were completed. The multiple-feature model performed better than the single-feature model on the test set, with an R² score of 0.5758 compared with 0.4589. The VIF results also indicated possible multicollinearity among some input features. The activity demonstrated that using additional features can improve prediction, but feature relationships and regression assumptions must also be checked. The model has limitations, including possible non-linear relationships, spatial dependence and factors not included in the dataset.

---

**Note:** The reported metrics are from the executed notebook using an 80:20 train-test split with `random_state=42`.
