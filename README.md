# USA Housing Price Prediction

This project uses machine learning techniques to predict housing prices in the USA based on various features of homes. The dataset includes information such as the number of bedrooms, bathrooms, square footage, and more. The goal is to build a model that can accurately predict the price of a house based on these features.

## Project Overview

### Dataset
The dataset used in this project is the **USA Housing Dataset**, which includes the following columns:
- **date**: Date when the house was listed.
- **price**: Target variable (price of the house).
- **bedrooms**: Number of bedrooms.
- **bathrooms**: Number of bathrooms.
- **sqft_living**: Square footage of the living area.
- **sqft_lot**: Size of the lot in square feet.
- **floors**: Number of floors in the house.
- **waterfront**: Whether the house is on the waterfront.
- **view**: View quality (score from 0 to 4).
- **condition**: Condition of the house.
- **sqft_above**: Square footage of the house excluding the basement.
- **sqft_basement**: Square footage of the basement.
- **yr_built**: Year the house was built.
- **yr_renovated**: Year the house was renovated (if applicable).
- **street**: Type of street the house is located on.
- **city**: City the house is located in.
- **statezip**: State and zip code of the house.
- **country**: Country of the house.

### Objective
To build a regression model that predicts house prices based on the features provided in the dataset.

---

## Steps Involved

### 1. Data Exploration and Preprocessing
- Loaded the dataset and performed basic inspection.
- Identified and handled missing values.
- Checked for outliers using **z-scores** and removed those with extreme values.
- Encoded categorical variables, such as **city**, **statezip**, and **street**, using appropriate encoding techniques.

### 2. Feature Engineering
- Created new features such as **total_sqft** (sum of living area and basement area) and **age_of_house** (current year minus the year built).
- Scaled numerical features using **StandardScaler** for consistency.

### 3. Model Training and Evaluation
- Split the data into **training** and **test** sets.
- Trained a **Linear Regression** model on the training data.
- Evaluated model performance using **R²**, **MAE**, and **RMSE**.

### 4. Model Comparison and Improvement
- Implemented a pipeline with **Imputer → StandardScaler → Linear Regression**.
- Tried adding **Polynomial Features (degree=3)** to the pipeline and compared performance.
- Found that the linear regression model (Pipeline 1) outperformed the polynomial model.

---

## Results

### Performance Metrics:
- **Pipeline 1 (Linear Regression)**:
  - **R²**: 0.4473
  - **MAE**: $142,083.41
  - **RMSE**: $198,457.71

- **Pipeline 2 (Polynomial Features + Linear Regression)**:
  - **R²**: 0.4367
  - **MAE**: $139,821.34
  - **RMSE**: $200,349.79

---

## Reflection and Insights
- **Linear Regression** performed slightly better than the **Polynomial Features** approach, as adding polynomial features led to minor overfitting.
- Scaling of the features helped ensure that all variables contributed equally to the model.
- Further model improvements could include trying more complex algorithms such as **Random Forest** or **Gradient Boosting**.

---

## Requirements
To run this project, you'll need the following Python libraries:
- **pandas**
- **numpy**
- **matplotlib**
- **seaborn**
- **scikit-learn**

To install the necessary libraries, use the following command: pip install -r requirements.txt

---

## Future Work
- Experiment with more advanced models like **Random Forest** and **Gradient Boosting** to see if they outperform linear regression.
- Perform **hyperparameter tuning** using tools like **GridSearchCV** to optimize model performance.
- Explore feature interactions and create new derived features to improve model accuracy.
