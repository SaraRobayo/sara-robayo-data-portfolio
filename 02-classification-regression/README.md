# Ejercicio 1 — Clasificación lineal

## Descripción
Este notebook desarrolla un ejemplo de clasificación binaria con un conjunto de datos sintético de dos dimensiones. Genera dos clases mediante distribuciones normales multivariadas, con medias simétricas respecto al origen, y compara dos enfoques de clasificación.

## Contenido y procedimiento
1. Generación de 300 observaciones por clase con una matriz de covarianza compartida.
2. Comprobación de que la media global de los datos sea aproximadamente cero.
3. Entrenamiento de `LogisticRegression` de scikit-learn.
4. Implementación de un clasificador personalizado que calcula `theta` como el promedio de los datos de la clase 1 y aplica la función sigmoide a `X @ theta`.
5. Comparación de ambos clasificadores mediante accuracy, matrices de confusión y reportes de clasificación.
6. Visualización de las regiones de decisión y de los puntos de ambas clases.

## Datos de entrada
No requiere archivos externos: el conjunto de datos se genera dentro del notebook usando NumPy.

## Bibliotecas
- NumPy
- pandas
- Matplotlib
- scikit-learn

## Ejecución
Abrir el archivo en Jupyter Notebook o JupyterLab y ejecutar las celdas en orden. Las métricas se calculan sobre el mismo conjunto generado y utilizado para entrenar; por tanto, el accuracy mostrado es de entrenamiento, no una evaluación sobre datos independientes.

## Alcance y consideración
El clasificador personalizado no optimiza una función de pérdida ni aprende un intercepto mediante un algoritmo de entrenamiento. Usa directamente el promedio de la clase 1 como vector de parámetros. El notebook permite contrastar esa regla heurística con la regresión logística de scikit-learn; no debe interpretarse como una implementación equivalente del entrenamiento de regresión logística.

# Ejercicio 2 — Clasificación de dígitos (MNIST o `digits`)

## Descripción
Este notebook compara métodos de clasificación para reconocer dígitos escritos a mano. Intenta utilizar MNIST mediante `fetch_openml`; si la descarga falla, utiliza el conjunto `digits` incluido en scikit-learn.

## Contenido y procedimiento
1. Carga de MNIST desde OpenML o selección alternativa de `sklearn.datasets.load_digits`.
2. Normalización inicial de los valores de píxel y selección aleatoria de hasta 3.000 observaciones para reducir el tiempo de ejecución.
3. Estandarización de las características con `StandardScaler`.
4. División estratificada en entrenamiento (75 %) y prueba (25 %).
5. Evaluación de K-Nearest Neighbors (KNN) para `k = 1, 3, 5, 7`.
6. Entrenamiento y evaluación de regresión logística One-vs-Rest y multinomial.
7. Visualización de los coeficientes de los clasificadores One-vs-Rest como mapas de calor cuando la cantidad de características permite reconstruir una imagen cuadrada.
8. Reporte de clasificación para el modelo multinomial.

## Datos de entrada
- Preferido: MNIST descargado desde OpenML (`mnist_784`).
- Alternativa: conjunto `digits` incluido en scikit-learn, utilizado automáticamente si no se puede cargar MNIST.

La ejecución puede requerir conexión a Internet para descargar MNIST. El conjunto alternativo `digits` tiene imágenes de 8 × 8 píxeles, mientras que MNIST utiliza imágenes de 28 × 28; por eso los resultados y la visualización de coeficientes dependen del conjunto que se haya cargado.

## Bibliotecas
- NumPy
- Matplotlib
- scikit-learn (`datasets`, `model_selection`, `neighbors`, `linear_model`, `multiclass`, `preprocessing`, `metrics`)

## Ejecución
Abrir el notebook en Jupyter Notebook o JupyterLab y ejecutar todas las celdas en orden. Revisar el mensaje `Dataset usado` para confirmar si se trabajó con MNIST o con `digits`.

## Consideraciones
La muestra de hasta 3.000 imágenes se selecciona antes de la división de entrenamiento y prueba. El `StandardScaler` se ajusta sobre esa muestra completa antes del `train_test_split`; para una evaluación metodológicamente más estricta, el escalador debería ajustarse únicamente con `X_train` y luego aplicarse a `X_test` para evitar fuga de información. Los mapas de calor se generan solo cuando el número de características es un cuadrado perfecto.

# Ejercicio 3 — Regresión lineal

## Descripción
Este notebook realiza un ejercicio de regresión con el archivo `Regression_Housing_Synthetic.csv`. Incluye inspección descriptiva de los datos, entrenamiento de modelos lineales y evaluación de sus predicciones.

## Contenido y procedimiento
1. Lectura del archivo CSV y visualización de las primeras filas y estadísticas descriptivas.
2. Definición de las variables predictoras como todas las columnas excepto la última; la última columna se toma como variable objetivo.
3. División de los datos en entrenamiento (75 %) y prueba (25 %), con `random_state=0`.
4. Si existe una sola variable predictora, ajuste de una regresión lineal simple, cálculo de MSE, MAE y R², y gráfica de los datos con la recta ajustada.
5. Si hay varias variables predictoras, ajuste de una regresión lineal multivariable y de un modelo con características polinómicas de grado 2.
6. Comparación de modelos mediante MSE y R², selección del modelo con mayor R² y visualización de sus residuos.
7. Presentación de coeficientes del modelo seleccionado (o de los primeros 20 coeficientes polinómicos, ordenados por magnitud absoluta).

## Datos de entrada
Requiere el archivo `Regression_Housing_Synthetic.csv`. El notebook contiene actualmente una ruta absoluta específica de un equipo:
`/Users/llara/Documents/IA/Proyecto 1/Regression_Housing_Synthetic.csv`, el e+archivo se encuentra en la carpeta `data`.

Esa ruta debe cambiarse por la ubicación real del CSV en el equipo donde se ejecute. Se recomienda guardar el CSV junto al notebook y utilizar una ruta relativa, por ejemplo `Regression_Housing_Synthetic.csv`.

## Bibliotecas
- pandas
- NumPy
- Matplotlib
- scikit-learn (`LinearRegression`, métricas, `train_test_split`, `PolynomialFeatures`)

## Ejecución
Ubicar el CSV en la ruta configurada dentro del notebook, verificar que la última columna sea la variable objetivo y ejecutar las celdas en orden.

## Consideraciones
La selección de la variable objetivo depende del orden de las columnas: el código considera objetivo la última columna. En el caso multivariable, la selección del modelo se realiza comparando R² en el conjunto de prueba.