# Exercise 1 — Linear Classification

## Description

This notebook develops a binary classification example using a synthetic two-dimensional dataset. It generates two classes from multivariate normal distributions, with means symmetric around the origin, and compares two classification approaches.

## Content and Procedure

1. Generation of 300 observations per class using a shared covariance matrix.
2. Verification that the overall mean of the data is approximately zero.
3. Training of a `LogisticRegression` model from scikit-learn.
4. Implementation of a custom classifier that calculates `theta` as the mean of the class 1 data points and applies the sigmoid function to `X @ theta`.
5. Comparison of both classifiers using accuracy, confusion matrices, and classification reports.
6. Visualization of decision regions and data points from both classes.

## Input Data

No external files are required: the dataset is generated directly within the notebook using NumPy.

## Libraries

- NumPy
- pandas
- Matplotlib
- scikit-learn

## Execution

Open the file in Jupyter Notebook or JupyterLab and run the cells in order. The metrics are calculated on the same generated dataset used for training; therefore, the reported accuracy represents training accuracy, not evaluation on independent data.

## Scope and Considerations

The custom classifier does not optimize a loss function or learn an intercept through a training algorithm. Instead, it directly uses the mean of class 1 as its parameter vector. The notebook allows this heuristic rule to be compared with scikit-learn's logistic regression; it should not be interpreted as an equivalent implementation of logistic regression training.

---

# Exercise 2 — Digit Classification (MNIST or `digits`)

## Description

This notebook compares classification methods for recognizing handwritten digits. It attempts to use MNIST through `fetch_openml`; if the download fails, it uses the `digits` dataset included in scikit-learn.

## Content and Procedure

1. Loading MNIST from OpenML or selecting the alternative `sklearn.datasets.load_digits` dataset.
2. Initial normalization of pixel values and random selection of up to 3,000 observations to reduce execution time.
3. Feature standardization using `StandardScaler`.
4. Stratified split into training (75%) and testing (25%) sets.
5. Evaluation of K-Nearest Neighbors (KNN) for `k = 1, 3, 5, 7`.
6. Training and evaluation of One-vs-Rest and multinomial logistic regression.
7. Visualization of One-vs-Rest classifier coefficients as heatmaps when the number of features allows reconstruction of a square image.
8. Classification report for the multinomial model.

## Input Data

- Preferred: MNIST downloaded from OpenML (`mnist_784`).
- Alternative: the `digits` dataset included in scikit-learn, automatically used if MNIST cannot be loaded.

Execution may require an Internet connection to download MNIST. The alternative `digits` dataset contains 8 × 8 pixel images, while MNIST uses 28 × 28 pixel images; therefore, results and coefficient visualizations depend on which dataset is loaded.

## Libraries

- NumPy
- Matplotlib
- scikit-learn (`datasets`, `model_selection`, `neighbors`, `linear_model`, `multiclass`, `preprocessing`, `metrics`)

## Execution

Open the notebook in Jupyter Notebook or JupyterLab and run all cells in order. Check the `Dataset used` message to confirm whether MNIST or `digits` was used.

## Considerations

The sample of up to 3,000 images is selected before splitting the data into training and testing sets. `StandardScaler` is fitted on the entire sample before `train_test_split`; for a stricter methodological evaluation, the scaler should be fitted only on `X_train` and then applied to `X_test` to prevent data leakage.

Heatmaps are generated only when the number of features is a perfect square.

---

# Exercise 3 — Linear Regression

## Description

This notebook performs a regression exercise using the `Regression_Housing_Synthetic.csv` file. It includes descriptive data inspection, linear model training, and prediction evaluation.

## Content and Procedure

1. Reading the CSV file and displaying the first rows and descriptive statistics.
2. Defining the predictor variables as all columns except the last one; the last column is used as the target variable.
3. Splitting the data into training (75%) and testing (25%) sets, with `random_state=0`.
4. If there is only one predictor variable, fitting a simple linear regression model, calculating MSE, MAE, and R², and plotting the data with the fitted regression line.
5. If there are multiple predictor variables, fitting a multivariable linear regression model and a model with degree-2 polynomial features.
6. Comparing models using MSE and R², selecting the model with the highest R², and visualizing its residuals.
7. Presenting the coefficients of the selected model (or the first 20 polynomial coefficients, sorted by absolute magnitude).

## Input Data

Requires the `Regression_Housing_Synthetic.csv` file. The notebook currently contains an absolute path specific to one computer:

`/Users/llara/Documents/IA/Proyecto 1/Regression_Housing_Synthetic.csv`

The file is located in the `data` folder.

This path must be changed to the actual location of the CSV file on the computer where the notebook is executed. It is recommended to store the CSV alongside the notebook and use a relative path, for example:

`Regression_Housing_Synthetic.csv`

## Libraries

- pandas
- NumPy
- Matplotlib
- scikit-learn (`LinearRegression`, metrics, `train_test_split`, `PolynomialFeatures`)

## Execution

Place the CSV file in the path configured within the notebook, verify that the last column is the target variable, and run the cells in order.

## Considerations

The target variable is selected based on column order: the code considers the last column to be the target. In the multivariable case, model selection is performed by comparing R² on the test set.
