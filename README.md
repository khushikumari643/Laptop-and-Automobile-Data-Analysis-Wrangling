# Laptop-and-Automobile-Data-Analysis-Wrangling
This project focuses on data analysis and wrangling of two distinct datasets: laptop pricing data and automobile data.It involves steps like data acquisition, cleaning missing values, standardizing data, binning continuous variables, and performing exploratory data analysis (EDA) to understand relationships between features and predict price factor.

## Data Sources
Laptop Pricing Dataset: Obtained from a CSV file hosted on cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud. This dataset contains features like Manufacturer, Category, Screen size, GPU, OS, CPU_core, RAM, Storage, Weight, and Price.
Automobile Characteristics Dataset (auto.csv): Obtained from a CSV file hosted on cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud. This dataset includes various automobile specifications such as symboling, make, fuel-type, engine-size, horsepower, and price.


# _Key Steps & Methodologies_
1. Data Loading and Initial Setup
The project begins by loading the automobileEDA.csv dataset into a pandas DataFrame.
Essential libraries such as seaborn, pandas, numpy, and matplotlib are imported for data manipulation and visualization.
## 2. Exploratory Data Analysis (EDA)
Regression Plots: Visualizations are used to explore the relationship between features like 'highway-mpg', 'peak-rpm', and 'price' using sns.regplot.
Residual Plots: A residual plot for 'highway-mpg' vs. 'price' helps in assessing the appropriateness of a linear model.
Distribution Plots: Actual vs. Fitted value distribution plots are generated to visually compare the predicted prices with actual prices, indicating the model's overall fit.
## 3. Model Development
Simple Linear Regression: A linear model is trained using 'highway-mpg' as the sole predictor for 'price'.
Multiple Linear Regression: A more complex model is developed using multiple features (horsepower, curb-weight, engine-size, highway-mpg) to predict 'price'.
Polynomial Regression: Polynomial models of varying degrees (e.g., degree 3 and degree 20) are applied to capture non-linear relationships, particularly for 'highway-mpg' vs. 'price'.
## 4. Model Evaluation
R-squared (R²): This metric is used to evaluate how well the model's predictions approximate the real data points. Higher R² values indicate better fit.
Mean Squared Error (MSE): Measures the average of the squares of the errors—that is, the average squared difference between the estimated values and the actual value. Lower MSE values indicate better accuracy.
Cross-Validation: cross_val_score and cross_val_predict are employed to assess model performance robustly and prevent overfitting by evaluating the model on different subsets of the data.
Overfitting/Underfitting Analysis: R² values for training and test data are compared to identify potential overfitting.
## 5. Model Refinement
Pipeline: A Pipeline is constructed using StandardScaler, PolynomialFeatures, and LinearRegression to streamline preprocessing and model training.
Ridge Regression: This regularization technique is applied to address multicollinearity and prevent overfitting, especially in polynomial models. The optimal alpha parameter is explored by plotting R² scores against different alpha values.
GridSearchCV: GridSearchCV is utilized to systematically search for the best alpha parameter for the Ridge model, optimizing its performance.


### _Conclusion_
Based on the R-squared and Mean Squared Error values, the Multiple Linear Regression model generally demonstrated the best performance, striking a good balance between fit and generalization compared to simple linear and polynomial regression models for this dataset.

Further refinement with Ridge Regression and hyperparameter tuning using GridSearchCV helped in optimizing model performance and managing complexity.
