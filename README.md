# CAR-PREDICTION PROJECT

## 📌 Step 1: Data Loading and Preprocessing

✅ Objective:
Prepare the dataset for regression modeling by cleaning and transforming the data.

🗃️ 1. Data Loading:
The dataset CarPrice_Assignment.csv was loaded using pandas.

Initial inspection revealed that the CarName column contains a combination of car brand and model.

🧹 2. Feature Engineering:
Car brand extraction: Extracted brand names from the CarName column using str.split() and .lower().

Spelling correction: Fixed inconsistent brand spellings such as:

vw, vokswagen → volkswagen

toyouta → toyota

maxda → mazda

porcshce → porsche

Dropped the CarName column after extracting useful brand info.

🏷️ 3. Feature and Target Split:
price was identified as the target variable y.

All other columns were assigned to X (features).

🔍 4. Data Type Segregation:
Categorical features were detected using X.select_dtypes(include='object')

Numerical features were detected using X.select_dtypes(include=np.number)

🧪 5. Preprocessing Pipeline:
Used ColumnTransformer to create a reusable preprocessing pipeline:

Numerical features:

Scaled using StandardScaler to normalize data.

Categorical features:

One-hot encoded using OneHotEncoder with drop='first' to avoid multicollinearity.

Handled unseen categories using handle_unknown='ignore'.

⚙️ Output:
A clean, consistent dataset ready for model training via pipelines.



## Step 2: Model Implementation

Trained the following regression models using Scikit-learn pipelines:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Gradient Boosting Regressor
- Support Vector Regressor

Used `ColumnTransformer` for preprocessing and evaluated performance on test data using:
- R² Score
- Mean Squared Error (MSE)
- Mean Absolute Error (MAE)

Plotted a bar chart comparing model performance.


## Step 3: Model Evaluation

All five regression models were evaluated using:
- **R² Score**: Measures how well the model explains the variance.
- **Mean Squared Error (MSE)**: Penalizes larger errors.
- **Mean Absolute Error (MAE)**: Measures average prediction error.

### 📊 Results Summary:

| Model                  | R² Score | MSE      | MAE     |
|------------------------|----------|----------|---------|
| Linear Regression      | ...      | ...      | ...     |
| Decision Tree          | ...      | ...      | ...     |
| Random Forest          | ...      | ...      | ...     |
| Gradient Boosting      | ...      | ...      | ...     |
| Support Vector Regressor | ...    | ...      | ...     |

> ⚡ **Best Performing Model**: *Gradient Boosting Regressor*  
It achieved the highest R² Score and balanced error metrics, making it the most effective in predicting car prices.
