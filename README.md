# Data Science Job Salary Analysis and Prediction 📊💰

## Description

This project analyzes a dataset of data science job salaries from 2020 onwards. It involves cleaning and preprocessing the data, performing exploratory data analysis (EDA) to uncover insights, engineering features for modeling, and building a predictive model (RandomForestRegressor) to estimate salaries in USD based on job attributes. The analysis includes model evaluation and feature importance assessment.

---

## Dataset 💾

The analysis uses the `Data Science Job Salaries.csv` dataset, which includes features like:

* `work_year`
* `experience_level` (Entry, Mid, Senior, Executive)
* `employment_type` (Full-time, Part-time, etc.)
* `job_title`
* `salary_in_usd` (Target Variable)
* `employee_residence` (Country)
* `remote_ratio` (Converted to Job Type: On-site, Hybrid, Remote)
* `company_location` (Country)
* `company_size` (Small, Medium, Large)

---

## Workflow ⚙️

1.  **Import Libraries:** Essential Python libraries like Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, and Country Converter were imported.
2.  **Load Data:** The dataset was loaded into a Pandas DataFrame.
3.  **Data Cleaning & Preprocessing:**
    * Dropped irrelevant columns (`Unnamed: 0`, original `salary`, `salary_currency`).
    * Renamed `salary_in_usd` to `salary`.
    * Removed duplicate rows.
    * Standardized categorical features by mapping abbreviations to full descriptions (e.g., 'MI' to 'Mid-level', 'FT' to 'Full-time', 'L' to 'Large').
    * Converted `remote_ratio` into a categorical `job_type`.
    * Converted country codes to country names using `country_converter`.
4.  **Exploratory Data Analysis (EDA):**
    * Visualized salary distribution (Histogram).
    * Analyzed mean salary by experience level (Bar Plot).
    * Compared salary distributions by job type and company size (Box Plot).
    * Identified top-paying job titles (Bar Plot).
5.  **Feature Engineering:**
    * Applied Label Encoding to `experience_level`.
    * Applied One-Hot Encoding to nominal categorical features.
    * Defined features (X) and the target variable (y).
    * Split data into training (75%) and testing (25%) sets.
    * Scaled numerical features (`work_year`, `experience_level_encoded`) using `StandardScaler`.
6.  **Predictive Modeling:**
    * Trained a `RandomForestRegressor` model with optimized hyperparameters (`n_estimators=150`, `max_depth=10`, etc.).
    * Made predictions on the test set.
7.  **Model Evaluation:**
    * Calculated MAE, MSE, RMSE, and R-squared (R²) score.
    * Visualized actual vs. predicted salaries (Scatter/Reg Plot).
8.  **Feature Importance:** Identified and plotted the most influential features for the model's predictions.

---

## Libraries Used 📚

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn (train\_test\_split, RandomForestRegressor, metrics, LabelEncoder, StandardScaler)
* Country Converter

---

## Results 📈

The RandomForestRegressor model achieved an **R-squared (R²) score of 0.48** on the test set. This indicates that the model explains roughly 48% of the variance in data science job salaries based on the features used.

* **Mean Absolute Error (MAE):** ≈ 32,785 USD
* **Root Mean Squared Error (RMSE):** ≈ 50,030 USD

Feature importance analysis highlighted factors like experience level, specific job titles (e.g., Principal Data Engineer, Financial Data Analyst), and possibly location as key drivers of salary predictions. 

---

## How to Use 🚀

1.  Ensure you have Python and the required libraries installed (`pip install pandas numpy matplotlib seaborn scikit-learn country_converter`).
2.  Place the `Data Science Job Salaries.csv` file in the same directory as the notebook or update the file path in the code.
3.  Run the Jupyter Notebook (`Data_Science_Job_Salaries.ipynb`) cells sequentially.

---

## Author

* **Pranay Kudale**
