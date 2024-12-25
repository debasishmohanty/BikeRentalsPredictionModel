# Bike Rental Prediction Model

This project involves predicting bike rental counts based on various environmental and seasonal factors using regression analysis. The model utilizes a dataset of historical bike rental data and applies exploratory data analysis, feature engineering, and linear regression techniques to predict rental counts accurately.

---

## **Dataset Description**

The dataset contains the following features:

- **Independent Variables**:
  - `yr`: Year (0 = 2018, 1 = 2019)
  - `temp`: Normalized temperature in Celsius.
  - `hum`: Normalized humidity.
  - `windspeed`: Normalized wind speed.
  - `season`: Season (categorical: Spring, Summer, Winter, Fall).
  - `weather`: Weather conditions (categorical: Clear, Cloudy, Rain).

- **Dependent Variable**:
  - `cnt`: Count of total bike rentals (target variable).

---

## **Objective**

The goal is to predict the `cnt` (bike rental count) using the given features and evaluate the model's performance using metrics like R².

---

## **Approach**

### **1. Data Preprocessing**
- Handled missing values and ensured all features were numeric.
- Created dummy variables for categorical features (`season` and `weather`) to allow for their inclusion in the regression model.
- Scaled numerical variables (`temp`, `hum`, `windspeed`) using standardization to improve model stability.

### **2. Exploratory Data Analysis (EDA)**
- Plotted relationships between `cnt` and independent variables to understand trends.
- Used pair-plots and correlation matrices to identify features with strong linear relationships with `cnt`.
  - `temp` showed the highest positive correlation with `cnt` (~0.63).

### **3. Feature Engineering**
- Applied one-hot encoding with `drop_first=True` to avoid multicollinearity in dummy variables.
- Ensured no perfect multicollinearity by checking Variance Inflation Factor (VIF).

### **4. Model Building**
- Trained a linear regression model using scikit learn LinearRegression method.
- Selected features based on Recursive Feature Elimination (RFE) and VIF.

### **5. Residual Analysis**
- Performed residual analysis to validate assumptions of linear regression:
  - Residuals were randomly scattered around zero, indicating a linear relationship.

---

## **Model Evaluation**

### **Performance Metrics**
- **R² Score**: 0.78
  - The model explains 78% of the variance in bike rental counts.

### **Insights from Coefficients**
- `yr`: Positive impact; bike rentals increased significantly in 2012 compared to 2011.
- `temp`: Strong positive correlation with rentals; warmer temperatures lead to higher rentals.
- `weather_Rain`: Strong negative impact; rentals drop significantly on rainy days.

---

## **Key Takeaways**
1. Environmental factors like `temp` and `weather` significantly influence bike rental counts.
2. Rainy weather has the most substantial negative effect on rentals.
3. The linear regression model performs reasonably well but could be improved further by addressing outliers and exploring non-linear relationships.

---

## **Next Steps**
- Investigate and handle outliers to improve model robustness.
- Explore polynomial and interaction terms for better model accuracy.
- Experiment with regularization techniques like Ridge and Lasso regression to reduce overfitting.
- Validate the model on additional datasets to ensure generalizability.

---

## **How to Run**

1. Clone the repository and install the required Python libraries.
2. Prepare the dataset in the appropriate format.
3. Run the Python script to preprocess data, train the model, and evaluate performance.
4. Analyze the output metrics and visualizations for insights.

---

## **Acknowledgments**
- Tools and libraries used: Python, pandas, numpy, matplotlib, seaborn, scikit-learn.
- Dataset source:
  Use of this dataset in publications must be cited to the following publication:

  [1] Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin   Heidelberg, doi:10.1007/s13748-013-0040-3.

@article{
	year={2013},
	issn={2192-6352},
	journal={Progress in Artificial Intelligence},
	doi={10.1007/s13748-013-0040-3},
	title={Event labeling combining ensemble detectors and background knowledge},
	url={http://dx.doi.org/10.1007/s13748-013-0040-3},
	publisher={Springer Berlin Heidelberg},
	keywords={Event labeling; Event detection; Ensemble learning; Background knowledge},
	author={Fanaee-T, Hadi and Gama, Joao},
	pages={1-15}
}

---

Feel free to contribute by raising issues or suggesting improvements to enhance the model further!
