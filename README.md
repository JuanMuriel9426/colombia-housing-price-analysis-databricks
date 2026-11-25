# colombia-housing-price-analysis-databricks
Análisis exploratorio y predictivo de los precios de vivienda en Colombia con Databricks. Implementación de arquitectura Medallion (Bronze, Silver y Gold), análisis estadístico, evaluación de distribución Gamma, modelos de machine learning y visualización de resultados mediante dashboards..
# Análisis Exploratorio y Modelo Predictivo de Precios de Vivienda en Colombia
 
## Descripción del proyecto
 
Este proyecto tiene como objetivo analizar los precios de las propiedades inmobiliarias en Colombia mediante herramientas de análisis de datos y Machine Learning en Databricks. Se desarrolla un proceso de análisis exploratorio (EDA), transformación y procesamiento de datos utilizando la arquitectura Medallion, con el propósito de identificar las variables que más influyen en el precio de las viviendas y construir modelos predictivos.
 
Adicionalmente, se realiza un análisis estadístico de la distribución de los precios, evaluando el ajuste a una distribución Gamma y comparándola con otras distribuciones probabilísticas.
 
## Objetivos
 
- Realizar un análisis exploratorio de los precios de vivienda en Colombia.
- Identificar las variables con mayor relación e importancia en la determinación del precio.
- Implementar una arquitectura de datos Medallion (Bronze, Silver y Gold).
- Analizar la distribución estadística de los precios de las propiedades.
- Construir modelos de Machine Learning para predecir los precios de vivienda.
- Crear dashboards interactivos para visualizar los resultados.
- Facilitar la consulta de información mediante herramientas de Genie en Databricks.
 
## Fuente de datos
 
El proyecto utiliza el conjunto de datos **Colombia Housing Properties Price**, disponible en Kaggle.
 
- **Dataset:** [Colombia Housing Properties Price](https://www.kaggle.com/datasets/julianusugaortiz/colombia-housing-properties-price/data)
- **Fuente:** Kaggle.
 
## Arquitectura Medallion
 
Se implementa la arquitectura Medallion para organizar el procesamiento de los datos en tres capas:
 
### 1. Bronze – Datos originales
 
En esta capa se cargan los datos originales del conjunto de datos, conservando su estructura inicial y sin aplicar transformaciones significativas.
 
**Tabla principal:**
- `housing_colombia.bronze.housing_raw`
 
### 2. Silver – Datos limpios y transformados
 
En esta capa se realiza el proceso de limpieza y preparación de los datos. Se incluyen actividades como:
 
- Identificación y tratamiento de valores nulos.
- Eliminación de registros duplicados.
- Conversión de variables a los tipos de datos correspondientes.
- Validación de precios y áreas de las propiedades.
- Creación de variables derivadas para enriquecer el análisis.
 
**Tabla principal:**
- `housing_colombia.silver.housing_clean`
 
### 3. Gold – Datos analíticos y predictivos
 
En esta capa se almacenan los datos procesados y los resultados de los análisis, preparados para su utilización en dashboards y modelos predictivos.
 
Entre las tablas propuestas se encuentran:
 
- `housing_model_data`: información preparada para el entrenamiento de modelos.
- `housing_predictions`: resultados de las predicciones.
- `housing_feature_importance`: importancia de las variables del modelo.
- `housing_price_metrics`: métricas de evaluación.
- `housing_price_distribution`: información estadística de la distribución de precios.
- `housing_city_summary`: resumen de precios por ubicación geográfica.
 
## Análisis Exploratorio de Datos (EDA)
 
Se desarrolla un análisis exploratorio para comprender el comportamiento de los datos y encontrar patrones relevantes en el mercado inmobiliario colombiano.
 
El análisis contempla:
 
- Estadísticas descriptivas de las variables.
- Distribución de los precios de las propiedades.
- Análisis de valores atípicos.
- Identificación de relaciones y correlaciones entre variables.
- Comparación de precios según ubicación geográfica.
- Análisis de características como área, habitaciones, baños y tipo de propiedad.
- Identificación de las variables que tienen mayor influencia en el precio de las viviendas.
 
Se utilizan visualizaciones estadísticas para facilitar la interpretación de los resultados y comprender los principales factores asociados al valor de las propiedades.
 
## Análisis de distribución de precios
 
Se realiza un análisis probabilístico de los precios de vivienda para evaluar su comportamiento y determinar si pueden representarse mediante una distribución Gamma.
 
Para ello, se contempla:
 
- Construcción de histogramas de los precios.
- Ajuste de una distribución Gamma a los datos.
- Estimación de los parámetros de la distribución.
- Comparación con otras distribuciones, como Lognormal y Weibull.
- Evaluación de los ajustes mediante criterios estadísticos como AIC, BIC y pruebas de bondad de ajuste.
 
Este procedimiento permite determinar qué distribución representa mejor el comportamiento de los precios, sin asumir previamente que la distribución Gamma es necesariamente la más adecuada.
 
## Modelo predictivo de Machine Learning
 
Se plantea la construcción de modelos de aprendizaje automático para estimar el precio de una vivienda a partir de sus características.
 
Se consideran los siguientes algoritmos:
 
- **Linear Regression:** modelo de regresión lineal utilizado como referencia inicial.
- **Random Forest Regressor:** algoritmo basado en múltiples árboles de decisión que permite identificar relaciones no lineales.
- **Gradient Boosting Regressor:** modelo de ensamble que combina diferentes árboles de decisión para mejorar la capacidad predictiva.
 
### Evaluación de los modelos
 
El desempeño de los modelos se evalúa mediante las siguientes métricas:
 
- **MAE (Mean Absolute Error):** mide el error absoluto promedio de las predicciones.
- **RMSE (Root Mean Squared Error):** mide la raíz del error cuadrático medio y penaliza los errores de mayor magnitud.
- **R² (Coeficiente de determinación):** permite evaluar qué proporción de la variabilidad del precio es explicada por el modelo.
 
También se analiza la importancia de las variables para identificar cuáles características tienen mayor capacidad explicativa en la predicción del precio.
 
## Dashboard en Databricks
 
Se plantea la construcción de un dashboard interactivo utilizando la información disponible en la capa Gold.
 
El dashboard se organiza en tres secciones principales:
 
### 1. Análisis general del mercado inmobiliario
 <img width="785" height="455" alt="image" src="https://github.com/user-attachments/assets/3058d4e7-f727-4139-82d8-153ae572e9c7" />

- Cantidad de propiedades analizadas.
- Precio promedio y mediano.
- Distribución de precios.
- Comparación de precios por ciudad o ubicación.
 
### 2. Análisis estadístico
<img width="812" height="445" alt="image" src="https://github.com/user-attachments/assets/465cac7c-254e-4c7b-8546-4561de6ebd3d" />

- Distribución de los precios de vivienda.
- Visualización de la función de densidad Gamma y otras distribuciones evaluadas.
- Análisis de correlaciones.
- Relación entre las características de las propiedades y sus precios.
 
### 3. Análisis predictivo
<img width="808" height="463" alt="image" src="https://github.com/user-attachments/assets/f9c0fca2-4ed3-4345-9cc1-60931e7cdd31" />

- Resultados de los modelos de Machine Learning.
- Comparación de métricas de desempeño.
- Importancia de las variables.
- Visualización de precios reales frente a precios predichos.
 
## Genie y Genie Code
 
Se contempla el uso de herramientas de inteligencia artificial de Databricks para apoyar el desarrollo y la consulta del proyecto.
 
**Genie Code** se utiliza como asistente para apoyar la generación, explicación y revisión de código durante las diferentes etapas del proyecto, incluyendo la exploración de datos, transformación, análisis estadístico y construcción de modelos.
 
**Genie** permite facilitar la consulta de la información mediante preguntas en lenguaje natural, utilizando como referencia las tablas analíticas de la capa Gold.
 
## Tecnologías y herramientas utilizadas
 
- **Databricks:** entorno principal para el procesamiento, análisis y desarrollo del proyecto.
- **Python:** lenguaje de programación.
- **PySpark:** procesamiento y transformación de datos.
- **Pandas:** manipulación y análisis de datos.
- **Matplotlib y Seaborn:** visualización de información.
- **SciPy:** análisis estadístico y ajuste de distribuciones probabilísticas.
- **Scikit-learn:** construcción y evaluación de modelos de Machine Learning.
- **Delta Lake:** almacenamiento y gestión de las tablas de la arquitectura Medallion.
- **Databricks AI/BI Dashboards:** visualización de resultados.
- **Genie y Genie Code:** consulta de datos y asistencia en el desarrollo.
 
## Resultados esperados
 
El desarrollo del proyecto busca obtener una visión general del comportamiento de los precios de vivienda en Colombia, identificar las características más relevantes para explicar su variación y construir un modelo capaz de estimar precios a partir de las propiedades disponibles.
 
Asimismo, se espera consolidar un flujo de trabajo completo de ingeniería y análisis de datos mediante la arquitectura Medallion, complementado con análisis estadístico, modelos predictivos y herramientas de visualización.
 
**Nota:** Los resultados definitivos, las variables más influyentes y el modelo con mejor desempeño deben establecerse a partir de la ejecución y validación de los análisis sobre el conjunto de datos.
 
---
 
## Etiquetas del proyecto
 
`Databricks` `Python` `PySpark` `Machine Learning` `EDA` `Medallion Architecture` `Delta Lake` `Housing Prices` `Data Science` `Genie` `Scikit-learn`
