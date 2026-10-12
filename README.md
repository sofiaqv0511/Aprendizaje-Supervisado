# Trabajo Práctico 2: Aprendizaje Supervisado
### Sofía Quiroz Valencia 
### Ciencia de Datos II

## 1. Descripción del proyecto

Este proyecto tiene como objetivo comparar diferentes modelos de clasificación supervisada para identificar variedades de fríjoles a partir de sus características físicas. Para ello, se utiliza el conjunto de datos **Dry Bean Dataset**, que contiene información numérica sobre diferentes características de los granos.

Se entrenan y evalúan tres modelos de clasificación para determinar cuál presenta el mejor desempeño y capacidad de generalización.

## 2. Dataset

Se utiliza el **Dry Bean Dataset**, disponible en el repositorio de la Universidad de California en Irvine (UCI).

- **Fuente:** Dry Bean Dataset
- **Número de observaciones:** 13.611.
- **Variables predictoras:** 16 variables numéricas.
- **Variable objetivo:** `Class`.
- **Número de clases:** 7 variedades de fríjoles.

## 3. Modelos utilizados

Se comparan los siguientes modelos de clasificación:

- **Regresión logística:** utilizada como modelo de clasificación de referencia.
- **K vecinos más cercanos (KNN):** clasifica las observaciones según la cercanía entre sus características.
- **Árbol de decisión:** realiza clasificaciones mediante reglas basadas en las variables predictoras.

Los modelos se implementan mediante pipelines que incluyen la estandarización de las variables numéricas.

## 4. Metodología

El desarrollo del proyecto incluye las siguientes etapas:

1. Carga y exploración del conjunto de datos.
2. Revisión de valores faltantes, duplicados y distribución de las clases.
3. Análisis descriptivo mediante gráficos y matriz de correlación.
4. Separación de los datos en entrenamiento (60 %), validación (20 %) y prueba (20 %), utilizando división estratificada.
5. Entrenamiento de los tres modelos con sus hiperparámetros predeterminados.
6. Evaluación mediante la métrica ROC AUC.
7. Aplicación de validación cruzada estratificada de cinco particiones.
8. Comparación de los resultados y selección del mejor modelo.
9. Evaluación final del modelo seleccionado sobre el conjunto de prueba.

## 5. Métrica de evaluación

La métrica principal es **ROC AUC**, calculada mediante el enfoque multiclase *One-vs-Rest* (OvR) y el promedio macro.

Esta métrica permite evaluar la capacidad del modelo para distinguir entre las diferentes variedades de fríjoles. Un valor más cercano a 1 indica un mejor desempeño de clasificación.

También se utiliza la matriz de confusión y el reporte de clasificación para analizar los resultados finales.

## 6. Resultados

La regresión logística presentó el mejor desempeño general entre los modelos evaluados.

| Evaluación | ROC AUC |
|---|---:|
| Entrenamiento | 0.9951 |
| Validación | 0.9951 |
| Promedio de validación cruzada | 0.9949 |
| Conjunto de prueba | 0.9943 |

La diferencia absoluta entre el promedio de validación cruzada y el resultado de prueba fue de **0.0006**, lo que evidencia resultados muy similares entre ambas evaluaciones.

En conclusión, la regresión logística fue seleccionada como el modelo más adecuado debido a su alto desempeño y estabilidad en los diferentes conjuntos de datos.

## 7. Tecnologías utilizadas

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Openpyxl

## 8. Estructura del repositorio

- `Trabajo_Practico_2.ipynb`: notebook con el desarrollo del proyecto, análisis, modelos y resultados.
- `Dry_Bean_Dataset.xlsx`: archivo de datos utilizado.
- `resultados_comparacion_modelos.csv`: tabla comparativa de los modelos.
- `resultados_validacion_cruzada.csv`: resultados de las cinco particiones de validación cruzada.

## 9. Cómo ejecutar el proyecto

1. Clonar o descargar este repositorio.
2. Instalar las librerías necesarias.
3. Ubicar el archivo `Dry_Bean_Dataset.xlsx` en la misma carpeta del notebook.
4. Abrir `Trabajo_Practico_2.ipynb` en Jupyter Notebook o Google Colab.
5. Ejecutar las celdas en orden.

## 10. Conclusión general

El ejercicio permitió comparar tres modelos clásicos de aprendizaje supervisado y evaluar su capacidad de clasificación mediante validación cruzada y un conjunto de prueba independiente. Los resultados muestran que la regresión logística obtuvo el mejor desempeño general, con valores ROC AUC superiores a los de KNN y el árbol de decisión. Además, la cercanía entre los resultados de validación cruzada y prueba respalda la estabilidad del modelo seleccionado para clasificar las variedades de fríjoles.
