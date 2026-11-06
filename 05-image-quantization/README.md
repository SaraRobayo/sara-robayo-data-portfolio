# Image Quantization

## Description
This notebook reduces the number of colors in RGB images using clustering techniques. The goal is to represent each image with a limited color palette and compare the reconstruction with the original image using the mean squared error (MSE).

## Contents and Methodology
1. Search for `.jpg` and `.png` files located in the current working directory (`./`).
2. Load and display the images found.
3. Define the `cuantizar_exact_k` function, which:
   - Converts pixels into RGB vectors.
   - Takes a random sample of pixels to fit the clustering algorithm when the image is large.
   - Supports either `KMeans` or `AgglomerativeClustering`.
   - Assigns all pixels to the nearest center in batches to control memory usage.
   - Reconstructs the image using the representative colors.
   - Calculates the MSE between the original pixels and their assigned colors.
4. Apply quantization to each image found.
5. Visually compare the original and quantized images and display the MSE for each image.

## Current Configuration
The execution cell uses `k = 9` colors and `metodo = "kmeans"`. The function allows these parameters to be modified and also supports `agglomerative`.

## Input Data
One or more `.jpg` or `.png` images must be placed in the same folder from which the notebook is executed. The search is not recursive: it does not include images located only in subfolders.

The images are currently stored in the `data` folder and must be moved to the same directory from which the notebook is executed.

## Libraries
- Python
- NumPy
- Pillow (`PIL`)
- Matplotlib
- scikit-learn (`KMeans`, `AgglomerativeClustering`, `pairwise_distances_argmin`, `mean_squared_error`)

## Execution
1. Install the required libraries.
2. Save the input images alongside the notebook or in the working directory from which Jupyter will be launched.
3. Run the cells in order.
4. Review the reconstructed images and their MSE values.

## Considerations
The MSE measures the numerical difference between the original RGB values and the reconstructed colors; a lower value indicates a smaller reconstruction error. For `KMeans`, the centroids are obtained from the sampled subset of pixels when the image exceeds `sample_size`. In the agglomerative case, the centroids are calculated as the mean of the pixels belonging to each cluster in that sample. The result depends on the random sample and the configured parameters.
