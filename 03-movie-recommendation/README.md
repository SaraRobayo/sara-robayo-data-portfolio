# Sistema de recomendación de películas — MovieLens 100k

## Descripción
Este notebook explora datos de calificaciones de películas y desarrolla componentes de análisis no supervisado y recomendación. Trabaja con información de ratings, géneros, títulos y datos demográficos de usuarios.

## Contenido y procedimiento
1. **Carga y análisis exploratorio:** distribución de calificaciones, películas más calificadas, promedios y densidad de la matriz usuario–película.
2. **Reducción de dimensionalidad y clustering de usuarios:** construcción de la matriz usuario–película, aplicación de `TruncatedSVD` y agrupación con `KMeans`; posteriormente se describen los clusters usando variables demográficas.
3. **Clustering de películas:** agrupación de películas a partir de sus vectores binarios de géneros y revisión de los géneros promedio de cada grupo.
4. **Recomendación item-based:** cálculo de similitud coseno entre películas a partir de los ratings y generación de un ranking para un usuario, ponderando las similitudes por la desviación de sus calificaciones respecto a un valor base de 3.0.
5. **Evaluación:** división de ratings por usuario en entrenamiento y prueba, predicción de una muestra de ratings y cálculo de RMSE, además de gráficos de predicciones y errores.
6. **Cold-start de usuarios:** función basada en géneros que recibe pares `(movie_id, rating)` y calcula puntajes para películas no calificadas por el usuario nuevo.
7. **Análisis demográfico:** construcción de perfiles de afinidad por género y comparación de promedios por grupos de edad, sexo y ocupación.

## Datos de entrada
El notebook declara los siguientes archivos del conjunto MovieLens 100k:
- `u_data_ratings.xls`
- `u_movies_genre.xls`
- `u_movies_items.xls`
- `u_user_info.xls`

Deben estar disponibles en las rutas que utilice la celda de carga. Los cuatro archivos se encuentran en la carpeta `data`.

## Bibliotecas
- pandas
- NumPy
- Matplotlib
- scikit-learn: `TruncatedSVD`, `KMeans`, `cosine_similarity` y métricas de evaluación.
- Un motor de lectura de Excel compatible con los archivos `.xls` (por ejemplo, `xlrd`, según la versión de pandas).

## Ejecución
1. Colocar los archivos de datos en la ubicación configurada en la celda de carga.
2. Instalar las dependencias requeridas, incluido el soporte para lectura de `.xls`.
3. Ejecutar las celdas en orden, ya que las etapas posteriores reutilizan objetos creados durante la carga y el análisis inicial.
4. Revisar las salidas, tablas y gráficas de cada sección.

## Consideraciones
- La matriz usuario–película es dispersa; en algunas etapas se reemplazan valores ausentes por cero para realizar operaciones de similitud o reducción de dimensión. Ese cero funciona como valor computacional y no equivale a una calificación observada.
- El recomendador item-based usa similitud coseno y un baseline fijo de 3.0; es un método sencillo, no un modelo avanzado de factorización.
- La evaluación reportada corresponde a una muestra de hasta 2.000 registros del conjunto de prueba.
- La función de cold-start usa producto punto entre vectores de géneros y ratings centrados en 3.0; no utiliza descripciones textuales de películas.
- El análisis demográfico describe diferencias agregadas entre grupos; por sí solo no demuestra que la demografía cause determinadas preferencias.
- El notebook contiene varias interpretaciones escritas junto a los resultados. Los valores concretos dependen de los archivos de datos y de la ejecución.
