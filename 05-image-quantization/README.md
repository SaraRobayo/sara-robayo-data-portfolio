# Cuantización de imágenes

## Descripción
Este notebook reduce la cantidad de colores presentes en imágenes RGB mediante técnicas de clustering. El objetivo es representar cada imagen con una paleta limitada y comparar la reconstrucción con la imagen original mediante el error cuadrático medio (MSE).

## Contenido y procedimiento
1. Búsqueda de archivos `.jpg` y `.png` ubicados en el directorio de trabajo actual (`./`).
2. Carga y visualización de las imágenes encontradas.
3. Definición de la función `cuantizar_exact_k`, que:
   - convierte los píxeles a vectores RGB;
   - toma una muestra aleatoria de píxeles para ajustar el clustering cuando la imagen es grande;
   - admite `KMeans` o `AgglomerativeClustering`;
   - asigna todos los píxeles al centro más cercano por bloques para controlar el uso de memoria;
   - reconstruye la imagen usando los colores representativos;
   - calcula el MSE entre los píxeles originales y los colores asignados.
4. Aplicación de la cuantización a cada imagen encontrada.
5. Comparación visual entre original y cuantizada, y presentación del MSE por imagen.

## Configuración actual
En la celda de ejecución se utiliza `k = 9` colores y `metodo = "kmeans"`. La función permite modificar esos parámetros y admite también `agglomerative`.

## Datos de entrada
Se deben colocar una o más imágenes `.jpg` o `.png` en la misma carpeta desde la que se ejecuta el notebook. La búsqueda no es recursiva: no incluye imágenes que estén únicamente en subcarpetas. Las imagenes se encuentran en la carpeta ´data´, se deben pasar a la misma carpeta de la que se ejecuta el notebook.

## Bibliotecas
- Python
- NumPy
- Pillow (`PIL`)
- Matplotlib
- scikit-learn (`KMeans`, `AgglomerativeClustering`, `pairwise_distances_argmin`, `mean_squared_error`)

## Ejecución
1. Instalar las bibliotecas necesarias.
2. Guardar las imágenes de entrada junto al notebook o en el directorio de trabajo desde el que se abrirá Jupyter.
3. Ejecutar las celdas en orden.
4. Revisar las imágenes reconstruidas y los valores de MSE.

## Consideraciones
El MSE mide la diferencia numérica entre los valores RGB originales y los colores reconstruidos; un valor menor representa menor error de reconstrucción. Para `KMeans`, los centroides se obtienen del subconjunto de píxeles muestreado cuando la imagen supera `sample_size`. En el caso aglomerativo, los centroides se calculan como la media de los píxeles de cada cluster de esa muestra. El resultado depende de la muestra aleatoria y de los parámetros configurados.
