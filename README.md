# 🏡 California Housing Price Prediction – Machine Learning Pipeline

This project predicts **California housing median values** based on features such as location, population, household characteristics, and income levels.  
It uses the **California Housing dataset** with **Scikit‑Learn Pipelines** for preprocessing and a **Random Forest Regressor** for modeling.

---

## 📌 Project Overview

- **Objective:** Build and deploy an end-to-end ML pipeline to predict median house prices.
- **Technologies:** Python, Pandas, NumPy, Scikit-learn, Joblib
- **Features:**
  - Stratified train-test splitting based on income category
  - Full preprocessing pipeline (handling missing values, scaling numeric features, one‑hot encoding categorical features)
  - Trained using `RandomForestRegressor`
  - Model and preprocessing pipeline saved for reuse
  - Inference mode to make predictions on new data

---

## 📂 Project Structure

📁 housing-price-prediction/

├── housing.csv # Dataset

├── main.py # Main pipeline & model script

├── model.pkl # Trained RandomForest model (generated after training)

├── pipeline.pkl # Preprocessing pipeline (generated after training)

├── input.csv # Training data subset used during inference

├── output.csv # Predictions output (generated after inference)

├── *.ipynb # Jupyter notebooks for data exploration & preprocessing

└── README.md

---

## ⚙️ How It Works

### 🔹 Training Phase
1. Reads `housing.csv` dataset.
2. Creates **income categories** for stratified sampling.
3. Splits into train/test while preserving income distribution.
4. Builds a preprocessing pipeline:
   - **Numeric features:** Median imputation + Standard Scaling
   - **Categorical features:** One‑Hot Encoding (`ocean_proximity`)
5. Trains a `RandomForestRegressor`.
6. Saves:
   - `model.pkl` (trained model)
   - `pipeline.pkl` (preprocessing steps)
   - `input.csv` (data sample used for inference)

### 🔹 Inference Phase
1. Loads `model.pkl` & `pipeline.pkl`.
2. Reads `input.csv` (features only).
3. Applies the pipeline & predicts house values.
4. Saves predictions to `output.csv`.

---

## 🚀 Installation & Usage

### 1️⃣ Clone the Repository
git clone https://github.com/ankithbalda/House_price_prediction.git
cd House_price_prediction

### 2️⃣ Install Dependencies
pip install pandas numpy scikit-learn joblib

### 3️⃣ Add Dataset
Place `housing.csv` (California Housing dataset) in the project directory.  
You can download it from Kaggle or use the provided one in the repository.

### 4️⃣ Run Training
python main.py
Output: Model trained and saved.

### 5️⃣ Run Inference
python main.py
Output: Inference complete. Results saved to output.csv

---

## 📊 Dataset Info

- **Source:** California housing survey data from 1990 (from StatLib / Kaggle).
- **Features:**
  - `longitude`, `latitude`
  - `housing_median_age`, `total_rooms`, `total_bedrooms`
  - `population`, `households`, `median_income`
  - `ocean_proximity` (categorical)
- **Target:**
  - `median_house_value`

---

## 🤝 Contributing
Contributions are welcome!  
Feel free to fork the repo and submit PRs for improvements, new models, or visualizations.

---
