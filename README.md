# 🏠 Housing Price Prediction

A machine learning project to predict California housing prices based on various features such as location, population, total rooms, and proximity to the ocean. The project includes data preprocessing, feature engineering, model training, hyperparameter tuning, and performance evaluation.

---

## 📂 Dataset

- **Source**: [California Housing Dataset](https://www.dcc.fc.up.pt/~ltorgo/Regression/cal_housing.html)
- **Format**: CSV
- **Target**: `median_house_value`

---

## 🧰 Libraries Used

- `pandas`, `numpy` — Data manipulation
- `matplotlib`, `seaborn` — Visualization
- `sklearn` — Modeling, preprocessing, evaluation

---

## 🧼 Data Preprocessing

- Handled missing values by dropping rows with `NaN`.
- One-hot encoded the categorical feature `ocean_proximity`.
- Log-transformed skewed features: `total_rooms`, `total_bedrooms`, `population`, `households`.
- Standardized numerical features using `StandardScaler`.

---

## 🧠 Feature Engineering

Created two new features to improve model performance:
- `bedroom_ratio = total_bedrooms / total_rooms`
- `household_rooms = total_rooms / households`

Explored correlation matrix and geographical distribution of prices.

---

## 🤖 Models Used

### 1. **Linear Regression**
- Baseline model for comparison.
- Evaluated using R² and RMSE.

### 2. **Random Forest Regressor**
- Robust model capturing non-linear relationships.

### 3. **Tuned Random Forest**
- Used `GridSearchCV` to optimize:
  - `n_estimators`
  - `max_depth`
  - `min_samples_split`

---

## 📈 Model Evaluation

| Model               | Training R² (%) | Testing R² (%) | Training RMSE | Testing RMSE |
|--------------------|------------------|----------------|---------------|--------------|
| Linear Regression   | ✅ _baseline_     | ✅              | ✅            | ✅           |
| Random Forest       | ✅                | ✅              | ✅            | ✅           |
| Tuned Random Forest | ✅                | ✅              | ✅            | ✅           |

Visualized actual vs predicted values for final tuned model.

---

## 📊 Results Visualization

- **Histograms** of features before and after transformation
- **Heatmap** of feature correlations
- **Scatter plot**: Latitude vs Longitude colored by price
- **Prediction plot**: Actual vs Predicted prices

---

## 📌 Key Takeaways

- Feature engineering like log-transformation and ratio features significantly improves performance.
- Random Forest outperformed Linear Regression.
- Hyperparameter tuning further boosted accuracy and reduced error.

---

## 🏁 How to Run

```bash
# Install required libraries
pip install pandas numpy matplotlib seaborn scikit-learn

# Run the script (make sure 'housing.csv' is in the same directory)
python housing_price_prediction.py
