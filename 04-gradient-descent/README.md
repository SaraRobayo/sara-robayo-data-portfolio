# Descenso del gradiente para regresión lineal

## Descripción
Este notebook implementa desde cero el algoritmo de descenso del gradiente para ajustar un modelo de regresión lineal utilizando un conjunto de datos de valoración inmobiliaria.

## Contenido y procedimiento
1. Importación de NumPy, pandas, Matplotlib, `StandardScaler` e `ipywidgets`.
2. Lectura del archivo Excel `Real_estate_valuation_data_set.xlsx`.
3. Selección de las variables predictoras mediante las columnas desde la segunda hasta la penúltima (`data.iloc[:, 1:-1]`) y de la variable objetivo mediante la última columna.
4. Estandarización de las variables predictoras con `StandardScaler`.
5. Implementación de la función de costo basada en el error cuadrático medio dividido entre `2m`.
6. Implementación de `gradient_descent`, que inicializa los parámetros en cero, agrega una columna de unos para el término independiente y actualiza los parámetros durante un número definido de iteraciones.
7. Visualización interactiva de la evolución del costo al variar la tasa de aprendizaje (`alpha`) mediante un control deslizante de `ipywidgets`. La ejecución configurada utiliza 100 iteraciones por valor seleccionado.

## Datos de entrada
Requiere el archivo Excel `Real_estate_valuation_data_set.xlsx` en el directorio de trabajo actual de Jupyter. El archivo se encuentra en la carpeta `data`.

## Bibliotecas
- NumPy
- pandas
- Matplotlib
- scikit-learn (`StandardScaler`)
- ipywidgets

## Ejecución
1. Instalar las dependencias.
2. Colocar el archivo Excel en el directorio de trabajo desde el que se ejecuta Jupyter, o modificar la ruta de lectura.
3. Ejecutar las celdas en orden.
4. Utilizar el deslizador para cambiar `alpha` y observar la curva de costo y los parámetros finales.

## Consideraciones
Solo se estandarizan las variables predictoras; la variable objetivo permanece en su escala original. La tasa de aprendizaje debe elegirse de forma que el costo disminuya y el algoritmo se mantenga estable. El control interactivo requiere que `ipywidgets` esté correctamente habilitado en el entorno de Jupyter. El notebook no implementa una división entrenamiento/prueba: el descenso del gradiente se ejecuta sobre todos los registros cargados.
