# Car Price Prediction Using Machine Learning

An end-to-end Machine Learning project designed to predict the Manufacturer's Suggested Retail Price (MSRP) of vehicles based on technical specifications and brand attributes. This project utilizes **Simple Linear Regression** for prediction and a **Decision Tree** for feature importance analysis, concluding with a web-based deployment using **Streamlit**.

## 📌 Project Overview
The automotive market's pricing is influenced by various factors such as engine power, drivetrain, and brand equity. 
This project aims to:
1.  **Identify** key variables that significantly impact car valuation.
2.  **Develop** a predictive model to estimate MSRP with high statistical confidence.
3.  **Deploy** an interactive dashboard for real-time price estimation and data visualization.

## 🛠️ Tech Stack
* **Language:** Python
* **Data Analysis:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (Linear Regression, Decision Trees)
* **Visualization:** Matplotlib, Seaborn, Plotly
* **Deployment:** Streamlit
* **Model Serialization:** Pickle

## 🚀 Machine Learning Pipeline

### 1. Data Preprocessing & Cleaning
* **Handling Missing Values:** Critical columns like `Horsepower` and `Torque` were imputed using brand-specific mean values to maintain data integrity.
* **Data Transformation:** Extracted numerical values from complex string features
* **Feature Engineering:**
    * Converted currency-based objects (MSRP) into floats.
    * Dropped high-cardinality/redundant columns: `index`, `Model`, `Trim`, and `Invoice Price`.
* **Encoding:** Applied One-Hot Encoding to categorical variables, resulting in a 36-feature input vector.

### 2. Exploratory Data Analysis (EDA)
* **Correlation Analysis:** Utilized Pearson correlation heatmaps to visualize the strong relationship between `MSRP`, `Horsepower_No`, and `Torque_No`.
* **Comparative Analysis:** Visualized the distribution of car makes against transmission types and engine aspirations using Seaborn pairplots.

### 3. Model Development & Evaluation
The project employs a **Linear Regression** model, achieving the following performance metrics:

| Metric | Training Set | Testing Set |
| :--- | :--- | :--- |
| **R² Score** | 0.8957 | 0.9198 |
| **RMSE** | 17421.78 | 16534.59 |

### 4. Feature Importance
Using a **Decision Tree Regressor**, the project identifies the top predictors of vehicle price:
1.  **Horsepower** (Most Significant)
2.  **Make (Manufacturer)**
3.  **Torque**
4.  **Engine Aspiration (Turbocharged)**

---

## 💻 Streamlit Web Application
The deployment phase features a multi-column Streamlit dashboard (`app.py`) that allows users to:
* **Input Features:** Adjust Horsepower, Torque, Body Style, and more via a sidebar.
* **Predict Price:** Generate an instant MSRP prediction using the serialized `.pkl` model.
* **Visualize Importance:** View an interactive Plotly bar chart displaying the variables that drive the model's logic.

### How to Run:
1.  **Install dependencies:**
    ```bash
    pip install pandas numpy scikit-learn streamlit plotly pillow openpyxl
    ```
2.  **Launch the App:**
    ```bash
    streamlit run app.py
    ```

---

## 📂 Project Structure
* `car_data.xlsx`: Raw vehicle dataset.
* `linear_model.pkl`: Trained Linear Regression model.
* `feature_importance.xlsx`: Exported feature scores from the Decision Tree.
* `app.py`: Streamlit application source code.
* `data_with_pred.xlsx`: Final dataset including model predictions.

##  Output
<img width="1437" height="813" alt="Output" src="https://github.com/user-attachments/assets/8a3e5e1f-3bb1-4f9e-b560-f0ade0016229" />
