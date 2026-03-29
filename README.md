# Mobile App Rating Prediction using Machine Learning

## Project Overview
This project builds a **machine learning model to predict mobile application ratings** using the Google Play Store dataset. The goal is to analyze application characteristics such as installs, reviews, category, size, and pricing to estimate how users might rate an application.

Predicting app ratings can help developers and product teams understand factors influencing user satisfaction and improve application quality.

In this project, I implemented an end-to-end machine learning workflow to analyze and predict mobile app ratings, including:
* Data cleaning and preprocessing
* Exploratory Data Analysis (EDA)
* Feature engineering
* Machine learning model training
* Model evaluation
* Interpretation of results

# Dataset
The dataset used in this project contains information about applications available on the [Google Play Store Apps](https://www.kaggle.com/datasets/lava18/google-play-store-apps).

### Key Features
* **App** – Application name
* **Category** – App category (e.g., Game, Business, Education)
* **Reviews** – Number of user reviews
* **Size** – Application size
* **Installs** – Number of installs
* **Type** – Free or Paid application
* **Price** – Price of the application
* **Content Rating** – Target audience rating
* **Genres** – App genre classification
* **Last Updated** – Last update date
* **Android Version** – Minimum Android version required
* **Rating (Target Variable)** – User rating of the application

The goal of the model is to **predict the Rating of an application** based on these features.

# Project Workflow
The project follows a standard **machine learning pipeline**.

## 1. Data Exploration
Initial analysis was performed to understand:
* dataset structure
* feature types
* missing values
* data distribution

Key functions used:
* `df.head()`
* `df.info()`
* `df.describe()`

# 2. Data Preprocessing
Real-world datasets often contain inconsistencies and missing values.
The following preprocessing steps were applied:
* Handling missing values
* Cleaning numeric columns such as:
  * **Installs**
  * **Reviews**
  * **Size**
  * **Price**
* Removing symbols and converting columns to numeric format
* Encoding categorical variables using **Label Encoding**
* Reordering dataset to keep the **target variable (Rating) at the end**

These steps ensured the dataset was suitable for machine learning.

# 3. Exploratory Data Analysis (EDA)
EDA was performed to understand relationships between features and ratings.

### Visualizations Created
* Rating Distribution
* Reviews vs Rating
* Correlation Heatmap
* Top 10 Categories by Installs

These visualizations helped identify patterns such as:
* Most apps have ratings between **4.0 and 4.5**
* Apps with more installs tend to receive more reviews
* Category influences app popularity

# 4. Machine Learning Models
Two regression models were implemented and compared.

### Linear Regression
A baseline model that assumes a linear relationship between input features and the target variable.

### Random Forest Regressor
An ensemble learning model that combines multiple decision trees to improve prediction performance and capture nonlinear relationships.

# Model Evaluation
Since the target variable is **continuous (ratings)**, regression metrics were used.

### Evaluation Metrics
* **R² Score** – Measures how well the model explains variation in ratings
* **MAE (Mean Absolute Error)** – Average absolute prediction error
* **MSE (Mean Squared Error)** – Penalizes larger errors more strongly

These metrics help assess the prediction performance of the models.

# Model Performance
Random Forest achieved better performance than Linear Regression.

Reason:
* Random Forest can capture **nonlinear relationships** between features
* It handles **mixed feature types** effectively
* It reduces overfitting through ensemble learning

However, the overall R² score is moderate. This is expected because app ratings are influenced by many qualitative factors such as:
* User experience
* App performance
* UI/UX design
* Bug frequency

These factors are **not included in the dataset**, limiting prediction accuracy.

# Model Diagnostics

### Actual vs Predicted Plot
This plot compares predicted ratings with actual ratings to evaluate prediction accuracy.

### Residual Analysis
Residual plots were used to analyze prediction errors and check whether errors were randomly distributed.

These diagnostics help assess the model’s behavior and reliability.

# Key Insights
* Most mobile apps receive ratings between **4.0 and 4.5**
* Applications with **more installs tend to receive more reviews**
* Popular app categories attract higher user engagement
* App ratings are influenced by multiple qualitative factors not present in the dataset
* Random Forest performs better than Linear Regression for this problem

# Technologies Used
* **Python**
* **Pandas** – Data manipulation
* **NumPy** – Numerical operations
* **Matplotlib & Seaborn** – Data visualization
* **Scikit-learn** – Machine learning models and evaluation
* **Jupyter Notebook** – Development environment

# Project Structure

```
Mobile-App-Rating-Prediction
│
├── notebook/
│   └── mobile_app_rating_prediction.ipynb
│
├── data/
│   └── google_play_store_dataset.csv
│
└── README.md
```

# How to Run the Project

1. Clone the repository

```bash
git clone https://github.com/ssrinidhx/mobile-app-rating-prediction.git
```

2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Run the notebook

```bash
jupyter notebook
```

Open:

```
mobile_app_rating_prediction.ipynb
```

# Skills Applied in This Project
This project demonstrates the following data science skills:
* Data Cleaning and Preprocessing
* Exploratory Data Analysis
* Feature Engineering
* Machine Learning Model Training
* Model Evaluation and Comparison
* Data Visualization
* Model Interpretation

# Conclusion

This project developed a machine learning model to predict mobile app ratings using application characteristics from the Google Play Store dataset.

Although the model captures some relationships between app features and ratings, the prediction accuracy remains moderate due to missing qualitative factors influencing user ratings.

Despite these limitations, the project demonstrates a **complete end-to-end machine learning pipeline**, from data preprocessing to model evaluation and interpretation.
