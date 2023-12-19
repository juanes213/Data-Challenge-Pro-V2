#### Nota: para Acceder al Dashboard, ingrese al siguiente enlance, ademas, por favor, usar la opcion de pantalla completa que encontrara en la zona inferior derecha de la pantalla para ajustar el tamaño del Dashboard al dispositivo.

https://ayrgthon.github.io/dcp.html

# Explorando la Riqueza Natural de La Guajira: Un Proyecto de Visualización Dinámica para Analizar y Conservar Especies en Peligro a través de un Tablero Interactivo de Biodiversidad
# Integrantes: Juan Esteban Albis, Jesús David Arevalo y Ayrgthon Soracá
## Descripción:
Este proyecto tiene como objetivo principal analizar y comprender la diversidad biológica en el departamento colombiano de La Guajira, específicamente en la región de Cerrejón. Para lograr esto, se ha recopilado un extenso conjunto de datos de biodiversidad entre los años 2005 y 2020, abarcando información sobre la presencia y ausencia de especies, así como su clasificación taxonómica.
El análisis se centra en la abundancia, riqueza y composición de especies en la región de Cerrejón, con el fin de identificar áreas prioritarias para la conservación y comprender las amenazas que enfrentan las especies más vulnerables.
Objetivos:
Objetivo General:
Implementar un tablero de visualización interactivo que permita analizar en detalle la biodiversidad en la región de Cerrejón, facilitando la comprensión de la diversidad biológica y orientando los esfuerzos de conservación.
Objetivos Específicos:
Cuantificar los niveles de abundancia y riqueza de especies a nivel general y por cada una de las 6 regiones evaluadas.
Identificar áreas prioritarias de alta biodiversidad que requieren protección especial.
Determinar los grupos taxonómicos presentes y sus características en distintos hábitats.
Clasificar las especies de mayor relevancia para la región y sus amenazas actuales.
Definir patrones de biodiversidad y distribución de especies en diferentes hot-spots de conservación.
Desarrollar informes personalizados para cada región sobre sus especies más representativas.
Presentar los datos de forma interactiva y en capas sucesivas para facilitar la comprensión por diferentes perfiles de usuarios.
Monitorear las especies raras de la zona para implementar planes de manejo.
Fomentar la educación y sensibilización sobre el capital natural de La Guajira.

# Información General Cerrejón:
Resultados Generales:
Abundancia total: 43,511 individuos
Riqueza total: 867 especies
Especies raras: 12,056
Distribución Geográfica:
El mapa muestra 6 regiones principales en el área de Cerrejón, con detalles sobre la abundancia y riqueza de especies en cada una:
Riohacha: 95 individuos y 25 especies
Albania: 11,541 individuos y 635 especies
Barrancas: 20,534 individuos y 702 especies
Hatonuevo: 9.864 individuos y 549 especies
Fonseca: 160 individuos y 10 especies
Maicao: 132 individuos y 73 especies
Composición de Especies:

En el primer gráfico, se exhibe una representación de barras que detalla las 11 clases más prevalentes en diversas regiones de zonas de extracción minera. Esta información reviste una importancia fundamental para evaluar y gestionar la peligrosidad de los impactos de la actividad minera en estas especies. Para un análisis más detallado sobre la distribución de dichas especies, se proporciona información adicional en el apartado dedicado a las "Especies".
1. Gonatodes vittatus
2. Lepidoblepharis sanctaemartae
3. Cnemidophorus  lemniscatus 
4. Ameiva bifrontata
5. Engystomops pustulosus  
6. Anolis auratus
7. Rhinella humboldti
8. Polioptila plumbea 
9. Alouatta seniculus
10. Furnarius leucopus
11. Cerdocyon Thous 

# Información Detallada por Región:
Al seleccionar una región específica, el dashboard proporciona información especializada para el área escogida, incluyendo:
Abundancia total
Riqueza de especies
Especies raras
Además, se presentan 3 gráficas:
Gráfico de barras con el número de especies raras por localidad.
Gráfico de barras con la cantidad de especies en Peligro según IUCN Red list of threatened species
Gráfico de burbujas que muestra información por categoría taxonómica, con el tamaño de la burbuja indicando la abundancia.
Finalmente, se incluye una tabla con columnas para cada categoría taxonómica y filas con información detallada de cada taxón en la región seleccionada, incluyendo conteos de especies por categoría.
Instrucciones de Uso:
Seleccionar Región: Utilizar la interfaz para seleccionar la región de interés.
Explorar Datos: Analizar las gráficas y tablas proporcionadas para obtener información detallada sobre la biodiversidad en la región seleccionada.
Filtrar por Rama Taxonómica: Utilizar los filtros interactivos para explorar la composición de especies por Taxón en diferentes ubicaciones geográficas.

# Modelado de Distribución de Especies
Descripción:
Este proyecto analiza datos de distribución de especies en el Valle del Cerrejón en Colombia con el objetivo de modelar la distribución de las especies mejor representadas en el conjunto de datos.
Objetivo: 
El objetivo central es comprender y prever la distribución espacial de las especies clave en el Valle del Cerrejón, utilizando datos de observaciones y registros biológicos. A través de técnicas avanzadas de modelado, se busca identificar patrones y factores que influyen en la presencia de estas especies en la región.



## 1. Preparación de Datos.
   
### 1.1 Funciones Auxiliares
En esta sección se definieron funciones auxiliares para mejorar la legibilidad del código y facilitar la preparación de datos. Estas funciones realizan tareas como listar variables en un directorio, generar puntos aleatorios en un GeoDataFrame, crear puntos de ausencia alrededor de áreas de presencia, contar especies por mes y año, y generar rutas a archivos de datos biológicos para un mes específico.

### 1.2 Clase Dataset
La clase Dataset se encarga de la preparación de datos. En el método __init__, se inicializa la clase con un DataFrame y el nombre de la especie. El método Preprocessing realiza la preparación inicial, filtrando por especie y generando un diccionario de coordenadas para cada fecha única. El método LogitPreprocess realiza un preprocesamiento específico para la regresión logística, incluyendo la creación de puntos de ausencia y la obtención de datos biológicos. Finalmente, dataset_creation crea un conjunto de datos codificado para la regresión logística, incorporando variables dummy para la categoría de monitoreo.

## 2. División de Datos.

En esta fase, se realizó la división del conjunto de datos en variables explicativas (X) y la variable objetivo (y). La variable objetivo representa la presencia o ausencia de la especie en cuestión. Se procedió a estandarizar las características, un paso crucial para garantizar que todas las variables tengan la misma escala. Esto es esencial para modelos que dependen de medidas de distancia, como la regresión logística y el soporte vectorial.
La división de los datos en conjuntos de entrenamiento y prueba permite evaluar la capacidad de generalización del modelo. El conjunto de entrenamiento se utiliza para entrenar el modelo, y el conjunto de prueba se reserva para evaluar su rendimiento en datos no vistos.

## 3. Entrenamiento de Modelos.
Búsqueda en Cuadrícula (Grid Search)
La búsqueda en cuadrícula es una técnica utilizada para ajustar los hiper parámetros de un modelo. Los hiper parámetros son configuraciones externas al modelo que afectan su rendimiento. En este proyecto, se aplicó la búsqueda en cuadrícula para encontrar la combinación óptima de hiper parámetros para cada modelo. La búsqueda se realiza evaluando el rendimiento del modelo en un conjunto de validación mediante validación cruzada.
Validación Cruzada Estratificada (Stratified K-Fold)
La validación cruzada estratificada es una técnica de validación cruzada que garantiza una distribución equitativa de las clases en cada fold. Dado que el conjunto de datos puede tener clases desequilibradas (presencia y ausencia de especies), la estratificación ayuda a prevenir problemas en los que una clase podría quedar subrepresentada en ciertos folds. En este caso, se utilizó una validación cruzada estratificada de 10 folds para evaluar los modelos de manera robusta.
Elección de Métrica: AUC-ROC
La métrica seleccionada para evaluar el rendimiento del modelo fue el Área Bajo la Curva de Características Operativas del Receptor (AUC-ROC). La curva ROC representa la tasa de verdaderos positivos frente a la tasa de falsos positivos en diferentes umbrales de clasificación. El AUC-ROC mide la capacidad del modelo para distinguir entre clases positivas y negativas. Un valor de AUC cercano a 1 indica un buen rendimiento, mientras que 0.5 indica un rendimiento aleatorio.

## 4. Evaluación de Modelos.

En esta sección, la elección de la métrica AUC-ROC como medida de rendimiento tiene una conexión directa con la formulación del problema y la inspiración tomada de modelos como MaxEnt y la regresión logística.
Probabilidad Condicional y Relación con MaxEnt y Regresión Logística.

La elección de abordar este problema desde la perspectiva de la probabilidad condicional, específicamente P(y=1|x), está fundamentada en el enfoque de modelos como MaxEnt y la regresión logística. En la regresión logística, se modela la probabilidad condicional de que la variable dependiente (en este caso, la presencia de la especie) sea igual a 1 dada una serie de variables independientes (las condiciones climáticas).
La métrica AUC-ROC se alinea perfectamente con esta perspectiva. Al evaluar la capacidad del modelo para distinguir entre clases positivas (presencia de la especie) y negativas (ausencia), se está midiendo la habilidad del modelo para modelar la probabilidad condicional. Si la curva ROC muestra un rendimiento cercano al azar (AUC-ROC cercano a 0.5), indica que las condiciones climáticas no están siendo un predictor efectivo de la presencia de la especie.
Importancia de la Probabilidad Aleatoria
La identificación de un rendimiento aleatorio en los modelos es crucial. Sugiere que las condiciones climáticas (variables independientes) no están proporcionando información útil para predecir la presencia de la especie. Esto podría indicar la presencia de factores externos no considerados en el modelo, como la actividad minera en la zona del Cerrejón. En otras palabras, si los modelos muestran un rendimiento aleatorio, nos está proporcionando una señal valiosa: las variables climáticas por sí solas no son suficientes para prever la presencia de la especie, y otros factores deben ser considerados.
La probabilidad condicional es fundamental en este contexto, ya que destaca la dependencia de la presencia de la especie en factores climáticos específicos. Si la probabilidad condicional resulta ser aleatoria, esto indica que el enfoque basado en condiciones climáticas no es suficiente para explicar la presencia de la especie, y se sugiere la exploración de otros factores.

# 5. Proceso de Inferencia y Generación de Mapas.

El proceso de inferencia y generación de mapas se realiza en varias etapas, desde el muestreo aleatorio del espacio del Cerrejón hasta la exportación de datos para su visualización en Tableau. Aquí se detalla cada paso:

## 5.1 Muestreo Aleatorio del Espacio del Cerrejón.

Se realiza un muestreo aleatorio del espacio del Cerrejón utilizando geometrías del conjunto de datos CNAT. Las coordenadas resultantes se almacenan en un DataFrame, y se generan puntos de ausencia alrededor de estas coordenadas utilizando la función create_absence_points.
## 5.2 Rasterización de Variables Climáticas.

Se rasterizan las variables climáticas en función de las coordenadas generadas. Se utiliza la función rasterio.open para leer archivos raster y muestrear valores en las coordenadas seleccionadas. Los datos resultantes se incorporan al DataFrame para su posterior procesamiento.
## 5.3 Predicción de P(y=1|x).

Utilizando los mejores modelos entrenados en la sección anterior, se realiza la predicción de la probabilidad condicional P(y=1∣x) para cada punto en el espacio del Cerrejón. Se utiliza un conjunto de variables climáticas como entrada para los modelos, y las predicciones se combinan en un conjunto final.
## 5.4 Exportación de Datos para el Heatmap en Tableau.

Los resultados de la inferencia, incluidas las coordenadas, las probabilidades predichas y las variables climáticas, se exportan a un archivo CSV llamado "ProbDist.csv". Este archivo se prepara para su uso en Tableau, donde se puede crear un heatmap para visualizar la distribución de probabilidades de presencia de la especie en el espacio del Cerrejón.
Este enfoque integral, desde el muestreo hasta la exportación de datos, permite una visualización efectiva de las probabilidades de presencia de la especie en el contexto geoespacial del Cerrejón. El uso de herramientas como Folium y la exportación de datos estructurados facilitan la creación de visualizaciones ricas e informativas.
