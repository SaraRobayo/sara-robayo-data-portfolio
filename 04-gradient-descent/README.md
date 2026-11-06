# Gradient Descent for Linear Regression

## Description
This notebook implements the gradient descent algorithm from scratch to fit a linear regression model using a real estate valuation dataset.

## Contents and Methodology
1. Importing NumPy, pandas, Matplotlib, `StandardScaler`, and `ipywidgets`.
2. Reading the Excel file `Real_estate_valuation_data_set.xlsx`.
3. Selecting the predictor variables using the columns from the second to the penultimate (`data.iloc[:, 1:-1]`) and the target variable using the last column.
4. Standardizing the predictor variables with `StandardScaler`.
5. Implementing the cost function based on the mean squared error divided by `2m`.
6. Implementing `gradient_descent`, which initializes the parameters to zero, adds a column of ones for the intercept term, and updates the parameters over a specified number of iterations.
7. Interactive visualization of cost evolution while varying the learning rate (`alpha`) using an `ipywidgets` slider. The configured execution uses 100 iterations for each selected value.

## Input Data
Requires the Excel file `Real_estate_valuation_data_set.xlsx` in the current Jupyter working directory. The file is located in the `data` folder.

## Libraries
- NumPy
- pandas
- Matplotlib
- scikit-learn (`StandardScaler`)
- ipywidgets

## Execution
1. Install the required dependencies.
2. Place the Excel file in the working directory from which Jupyter is running, or modify the file path.
3. Run the cells in order.
4. Use the slider to change `alpha` and observe the cost curve and final parameter values.

## Considerations
Only the predictor variables are standardized; the target variable remains on its original scale. The learning rate must be selected so that the cost decreases and the algorithm remains stable. The interactive control requires `ipywidgets` to be properly enabled in the Jupyter environment. The notebook does not implement a train/test split: gradient descent is performed using all loaded records.
