#  RetailMax Analytics: Big Data & ML Pipeline

Este proyecto implementa un pipeline de datos escalable para **RetailMax**, una plataforma de e-commerce que busca optimizar su estrategia de marketing mediante la identificación de clientes de alto valor ("High Spenders").

##  Descripción del Proyecto
El objetivo es procesar grandes volúmenes de datos de comportamiento de usuarios (sesiones, tiempo en app, antigüedad) para predecir si un cliente superará el umbral de gasto de **500 USD anuales**.

La solución utiliza **Apache Spark** para garantizar que el proceso sea distribuido y pueda escalar de miles a millones de registros sin cambios en la arquitectura.

##  Stack Tecnológico
* **Lenguaje:** Python (PySpark)
* **Motor de procesamiento:** Apache Spark 3.x
* **ML:** Spark MLlib (Logistic Regression, Pipelines)
* **SQL:** Spark SQL para analítica descriptiva
* **Almacenamiento:** Formato Parquet (columnar)

##  Arquitectura del Pipeline
1. **Ingesta:** Lectura de datos crudos con inferencia de esquema.
2. **Transformación:** Limpieza de nombres de columnas y feature engineering vía SQL.
3. **ML Pipeline:**
   - `VectorAssembler`: Consolidación de variables numéricas.
   - `StandardScaler`: Normalización de características.
   - `LogisticRegression`: Clasificación binaria de gasto.
4. **Evaluación:** Medición de precisión mediante el área bajo la curva (AUC).

##  Resultados Clave
* **Métrica AUC:** `0.7989` (Alta capacidad predictiva).
* **Insights de Negocio:** Se identificó que la **antigüedad de la membresía** es el predictor más fuerte para clientes VIP, mientras que el tiempo en la app muestra una correlación secundaria.
* **Eficiencia:** El uso de almacenamiento en **Parquet** reduce el peso de los datos y acelera las consultas de BI.

##  Estructura del Repositorio
* `notebooks/`: Archivo .ipynb con el flujo completo en PySpark.
* `output/`: Resultados del procesamiento en formato Parquet.
* `reports/`: Informe técnico final en PDF.