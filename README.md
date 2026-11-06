# Sara Sofia Robayo Negrete | Data Portfolio

Welcome to my data portfolio! I am a Mechatronics Engineer interested in **Data Analytics, Data Engineering, and Business Intelligence**. This repository brings together academic and personal projects in which I apply programming, data processing, statistical analysis, machine learning, and data visualization to practical problems.

My goal is to transform raw data into meaningful insights and build analytical solutions that support data-driven decision-making.

## About Me

My background combines engineering problem-solving with data analysis and business intelligence. Through academic and personal projects, I have worked with data preparation, exploratory analysis, data modeling, machine learning, and interactive reporting.

### Technical Skills

- **Programming:** Python, SQL, MATLAB.
- **Data Analysis:** Pandas, NumPy, data cleaning, exploratory data analysis (EDA), statistical analysis.
- **Data Visualization & BI:** Power BI, DAX, Power Query, Microsoft Excel.
- **Machine Learning:** Classification, regression, clustering, dimensionality reduction, recommendation systems.
- **Data Management:** ETL processes, data transformation, relational data, data modeling.
- **Tools:** Jupyter Notebook, Git, GitHub, scikit-learn.

## Projects

This portfolio contains five projects covering business intelligence, supervised and unsupervised learning, optimization, recommendation systems, and image processing.

### 1. PitWall Analytics — Formula 1 Data Analysis

**Folder:** `01-data-analytics/`

An interactive Business Intelligence project exploring historical Formula 1 data from 1950 to 2024.

- Prepared and transformed related CSV datasets using Power Query.
- Built a star-schema data model with `results` as the fact table and `drivers`, `constructors`, `races`, and `circuits` as dimensions.
- Created calculated columns and DAX measures to analyze race, driver, constructor, qualifying, pit-stop, and circuit-related metrics.
- Designed an interactive Power BI report with multiple pages and filters.
- Evaluated the report with a small group of five users and used their feedback to improve its clarity and usability.

**Main tools:** Power BI, Power Query, DAX, data modeling, ETL.

### 2. Classification and Regression

**Folder:** `02-classification-regression/`

A collection of three supervised-learning exercises covering binary classification, handwritten-digit recognition, and linear regression.

- Compared scikit-learn's logistic regression with a custom heuristic classifier on a synthetic two-class dataset.
- Evaluated K-Nearest Neighbors (KNN) and One-vs-Rest and multinomial logistic regression for handwritten-digit classification, using MNIST when available and scikit-learn's `digits` dataset as a fallback.
- Explored simple and multiple linear regression, including polynomial features, using a synthetic housing dataset.
- Evaluated models with classification metrics, confusion matrices, MSE, MAE, and R², as applicable.

**Main tools:** Python, Jupyter Notebook, NumPy, Pandas, Matplotlib, scikit-learn.

### 3. Movie Recommendation System

**Folder:** `03-movie-recommendation/`

A recommendation and exploratory-analysis project based on the MovieLens 100K dataset.

- Explored rating distributions, popular movies, and user–movie interactions.
- Applied Truncated SVD and K-Means to investigate user groups.
- Clustered movies using their genre attributes.
- Implemented item-based collaborative filtering using cosine similarity.
- Built a genre-based recommendation approach for users with no prior history (a simplified user cold-start scenario).
- Evaluated a sample of predictions using RMSE and explored rating patterns across demographic groups.

**Main tools:** Python, Pandas, NumPy, Matplotlib, scikit-learn, recommendation systems.

### 4. Gradient Descent

**Folder:** `04-gradient-descent/`

An implementation of the gradient descent optimization algorithm from scratch to fit a linear regression model using a real-estate valuation dataset.

- Prepared and standardized the predictor variables.
- Implemented the cost function and iterative parameter updates using NumPy.
- Explored how the learning rate affects the optimization process.
- Used an interactive `ipywidgets` control to inspect the cost curve and fitted parameters across learning-rate values.

**Main tools:** Python, Jupyter Notebook, NumPy, Pandas, Matplotlib, scikit-learn, ipywidgets.

### 5. Image Quantization

**Folder:** `05-image-quantization/`

An image-processing project that reduces the number of colors in RGB images using clustering.

- Represented image pixels as RGB feature vectors.
- Applied K-Means or Agglomerative Clustering to obtain a reduced color palette.
- Reconstructed images using representative cluster colors.
- Compared original and quantized images visually and calculated mean squared error (MSE).

**Main tools:** Python, NumPy, Pillow, Matplotlib, scikit-learn, clustering.

## Repository Structure

```text
sara-robayo-data-portfolio/
│
├── README.md
│
├── 01-data-analytics/
│   ├── Dasboard final proyecto Formula 1.pbix
│   ├── data/
│   ├── images/
│   └── README.md
│
├── 02-classification-regression/
│   ├── notebooks/
│   ├── data/
│   └── README.md
│
├── 03-movie-recommendation/
│   ├── notebook/
│   ├── data/
│   ├── images/
│   └── README.md
│
├── 04-gradient-descent/
│   ├── notebook/
│   ├── data/
│   └── README.md
│
└── 05-image-quantization/
    ├── notebook/
    ├── images/
    └── README.md
```

## Contact

I am interested in opportunities related to Data Analytics, Data Engineering, and Business Intelligence.

- **LinkedIn:** [Sara Robayo](https://www.linkedin.com/in/sara-robayo-negrete/)
- **Location:** Bogotá, Colombia

Thank you for visiting my portfolio!
