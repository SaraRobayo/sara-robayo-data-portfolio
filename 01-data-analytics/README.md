# **PitWallAnalytics** 

Pontificia Universidad Javeriana _·_ Visualización de Datos _·_ Mayo 2026 _|_ Sara Sofía Robayo Negrete

**1.125 mil 861 212 75 42,3 % 22,1 %** Carreras analizadas Pilotos únicos Constructores Temporadas (1950–2024) Tasa Pole _→_ Victoria Tasa falla mecánica 

## **1.125 mil** 

### **Hallazgos Principales** 

### **Conclusiones** 

- **Ferrari lidera el ranking histórico** con más de 240 victorias, seguido por McLaren (182) y Mercedes (125). El gráfico de áreas evidencia ciclos claros de dominancia: Ferrari en los 2000s, Red Bull entre 2010–2013 y Mercedes en 2014–2021. 

- **La pole position es ventajosa pero no decisiva.** La tasa de conversión pole _→_ victoria es del 42,3 %; en más del 57 % de las carreras, el ganador salió desde la segunda posición o más atrás, lo que subraya el peso determinante de la estrategia de carrera. 

- **Mónaco y Phoenix: menor índice de remontada** con valores negativos de hasta _−_ 8 posiciones en promedio. En trazados urbanos estrechos la posición de salida es prácticamente definitoria del resultado final. 

- **22,1 % de falla mecánica histórica.** Refleja la evolución tecnológica del deporte: la tasa de abandono mecánico en los años 50–70 superaba el 50 %, mientras que en la era moderna se ubica por debajo del 10 %. 

- **Pilotos británicos lideran en victorias por nacionalidad** con más de 300 triunfos históricos, seguidos por alemanes (214) y brasileños (101), confirmando al Reino Unido como la cuna de la Fórmula 1. 

- **Monza: el circuito más democrático** con _≈_ 40 pilotos distintos ganadores en su historia. Contrasta con circuitos modernos donde la dominancia de un equipo reduce severamente la diversidad de ganadores. 

- **Fuente de datos robusta y relacional.** El dataset _Formula 1 World Championship (1950–2024)_ de Kaggle, con 14 archivos CSV vinculados por claves primarias y foráneas, constituyó una base sólida para construir un modelo de BI de alta complejidad. 

- **Esquema en Estrella eficiente.** Con `results` como tabla de hechos y cuatro dimensiones ( `drivers` , `constructors` , `races` , `circuits` ), el modelo resolvió los cinco objetivos de visualización, incluyendo los dos de fuentes cruzadas (Obj. 3 y 5). 

- **Ingeniería de características determinante.** Las columnas _Finalizo_ , _Falla Mecánica_ , _Accidente_ y _RemontadaF_ , más las medidas DAX especializadas, habilitaron visualizaciones imposibles de construir directamente con los datos crudos. 

- **Estrategia de carrera tan relevante como la clasificación.** El hallazgo del 57,7 % de victorias sin pole implica que los equipos cliente deben equilibrar inversión en rendimiento de clasificación con planificación de estrategia de pit stops. 

- **Alta satisfacción en validación con usuarios:** 4,6/5 en claridad, 4,8/5 en diseño visual y 100 % de recomendación. Ajuste posterior: reducción de densidad visual en páginas multi-gráfico. 

- **Expansión global de la Fórmula 1** visible en el mapa geográfico: de concentración europea histórica a presencia creciente en Asia, Oriente Medio y América, tendencia que se intensifica desde 2010. 

### **Análisis de Resultados** 

Los resultados obtenidos permiten trazar una narrativa coherente sobre la evolución de la Fórmula 1 en 75 temporadas. La dominancia cíclica de Ferrari, Red Bull y Mercedes es inmediatamente visible en el gráfico de áreas de la Página 3. El análisis de _qualifying_ (Objetivo 3), al cruzar el Dataset 1 con el Dataset 2, revela que existe una correlación positiva entre posición de salida y resultado, pero con dispersión notable: la estrategia de pit stops (Objetivo 4) puede revertir hasta 8 posiciones en circuitos favorables. El mapa geográfico (Objetivo 5) confirma la concentración histórica en Europa y la expansión reciente hacia Oriente Medio y América. En conjunto, **PitWall Analytics** demuestra que los datos abiertos de la F1 permiten generar _insights_ accionables para equipos, medios y plataformas de fantasy racing. 

PitWall Analytics _·_ Pontificia Universidad Javeriana _·_ Visualización de Datos _·_ 2026 

**PitWall Analytics — Anexo Ejecutivo** 

Objetivos de Visualización _·_ Resultados de Validación _·_ Recomendaciones Estratégicas 

### **Objetivos de Visualización del Proyecto** 

|**#**|**Objetivo**|**Indicador Principal**|**Datasets**|**Multi-**<br>**fuente**|
|---|---|---|---|---|
|1|**Rendimiento histórico de**<br>**pilotos**|Tasa de conversión pole_→_victoria (42,3 %)|DS1|No|
|2|**Análisis de constructores**|Índice de fiabilidad por constructor (% carreras finalizadas)<br>|DS1|No|
|3|**Impacto del qualifying en**|Índice de remontada promedio por circuito|DS1 + DS2|**Sí**|
||**carrera**||||
|4|**Estrategia de pit stops**|Correlación pit stops vs. posición final por circuito<br>|DS3|No|
|5|**Análisis geográfico de vic-**<br>**torias**|Índice de diversidad de ganadores por circuito|DS1 + DS3|**Sí**|



### **Resultados de Validación con Usuarios** 

### **Recomendaciones Estratégicas** 

Se aplicó una encuesta estructurada a 5 usuarios (compañeros de asignatura, aficionados a la F1 y usuarios sin experiencia en BI) con siete preguntas en escala Likert 1–5 más una dicotómica. 

|**Aspecto evaluado**|**Promedio**|
|---|---|
|Claridad del propósito|**4,6 / 5**|
|Interpretabilidad de gráficos|3,8 / 5|
|Usabilidad de filtros|4,2 / 5|
|Diseño visual|**4,8 / 5**|
|Utilidad de la información|4,2 / 5|
|Recomendaría la herramienta|**100 % Sí**|



#### **Ajustes realizados tras la validación:** 

- Reducción de densidad visual eliminando elementos redundantes en páginas con múltiples gráficos simultáneos. 

- Reorganización de filtros temporales para facilitar la exploración de rangos de temporadas específicos. 

- Priorización de los gráficos más relevantes por página, mejorando la interpretabilidad general del reporte. 

Con base en los hallazgos del proyecto, se formulan las siguientes recomendaciones para los clientes de PitWall Analytics: 

- **Para equipos constructores:** invertir en estrategia de pit stops tiene un retorno comparable al de rendimiento de clasificación. El 57,7 % de victorias sin pole confirma que la carrera puede ganarse (o perderse) en el pitlane. 

- **Para circuitos urbanos** (Mónaco, Bakú, Las Vegas): la prioridad debe ser maximizar la clasificación, dado que el índice de remontada es estructuralmente negativo en estas pistas. 

- **Para medios especializados:** el índice de diversidad de ganadores por circuito es un indicador narrativo potente para enriquecer la cobertura editorial histórica y contextualizar temporadas actuales. 

- **Para plataformas de fantasy racing:** la tasa pole _→_ victoria (42,3 %) y el índice de fiabilidad por constructor (22,1 % falla mecánica histórica) son variables predictivas de alto valor para modelos de puntuación. 

- **Próximos pasos:** incorporar datos de 2025 una vez disponibles en Ergast/OpenF1 API, y ampliar el análisis de tiempos de vuelta ( `lap_times.csv` ) para modelar degradación de neumáticos por circuito. 

### **Fuentes de Datos y Tecnologías Utilizadas** 

|**Componente**|**Detalle**|**Propósito en el proyecto**|
|---|---|---|
|**Dataset princi-**|_F1 World Championship 1950–_|14 archivos CSV con resultados, pilotos, constructores y circuitos|
|**pal**|_2024_(Kaggle, rohanrao)||
|**Herramienta BI**|Microsoft Power BI Desktop|Modelado, ETL (Power Query), DAX y visualización interactiva|
|**Modelo**<br>**de**|Esquema<br>en<br>Estrella<br>(Star|`results`como tabla de hechos central con 4 dimensiones|
|**datos**|Schema)||
|**Fuente de API**|Ergast Motor Racing Data API|Base del dataset Kaggle; permite actualización con temporadas futuras|
|**Validación**|Google Forms (encuesta a 5 usuar-<br>ios)|Evaluación de claridad, usabilidad y diseño del reporte dinámico|



PitWall Analytics _·_ Pontificia Universidad Javeriana _·_ Visualización de Datos _·_ 2026 

