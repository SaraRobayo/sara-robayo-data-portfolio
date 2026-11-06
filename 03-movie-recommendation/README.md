# Movie Recommendation System — MovieLens 100k

## Description
This notebook explores movie rating data and develops components for unsupervised analysis and recommendation. It works with information on ratings, genres, titles, and user demographics.

## Contents and Methodology
1. **Data Loading and Exploratory Data Analysis:** rating distributions, most-rated movies, average ratings, and user–movie matrix density.
2. **Dimensionality Reduction and User Clustering:** construction of the user–movie matrix, application of `TruncatedSVD`, and clustering with `KMeans`; clusters are then described using demographic variables.
3. **Movie Clustering:** grouping movies based on their binary genre vectors and reviewing the average genres of each cluster.
4. **Item-Based Recommendation:** calculation of cosine similarity between movies based on ratings and generation of a ranking for a user, weighting similarities according to the deviation of their ratings from a baseline value of 3.0.
5. **Evaluation:** splitting each user's ratings into training and test sets, predicting a sample of ratings, and calculating RMSE, along with prediction and error plots.
6. **User Cold-Start:** a genre-based function that receives `(movie_id, rating)` pairs and calculates scores for movies that have not been rated by a new user.
7. **Demographic Analysis:** construction of genre affinity profiles and comparison of average ratings across age, gender, and occupation groups.

## Input Data
The notebook references the following files from the MovieLens 100k dataset:
- `u_data_ratings.xls`
- `u_movies_genre.xls`
- `u_movies_items.xls`
- `u_user_info.xls`

These files must be available at the paths specified in the data-loading cell. All four files are located in the `data` folder.

## Libraries
- pandas
- NumPy
- Matplotlib
- scikit-learn: `TruncatedSVD`, `KMeans`, `cosine_similarity`, and evaluation metrics.
- An Excel reading engine compatible with `.xls` files (e.g., `xlrd`, depending on the pandas version).

## Execution
1. Place the data files in the location configured in the data-loading cell.
2. Install the required dependencies, including support for reading `.xls` files.
3. Run the cells in order, since later stages reuse objects created during data loading and initial analysis.
4. Review the outputs, tables, and plots in each section.

## Considerations
- The user–movie matrix is sparse; in some stages, missing values are replaced with zeros to perform similarity or dimensionality reduction operations. This zero is used as a computational value and does not represent an observed rating.
- The item-based recommender uses cosine similarity and a fixed baseline of 3.0; it is a simple method, not an advanced matrix factorization model.
- The reported evaluation is based on a sample of up to 2,000 records from the test set.
- The cold-start function uses the dot product between genre vectors and ratings centered around 3.0; it does not use textual movie descriptions.
- The demographic analysis describes aggregated differences between groups; by itself, it does not demonstrate that demographics cause specific preferences.
- The notebook contains several written interpretations alongside the results. Specific values depend on the data files and the execution.
