# Tumor de Cervix - Algoritmo de Machine Learning

Este documento contiene información detallada sobre el proyecto de desarrollo de un algoritmo de Machine Learning para la clasificación de imágenes de tumores de cuello uterino (Cervix). El objetivo principal es asignar el tipo de tratamiento adecuado para cada caso basado en imágenes de los tumores. El proceso incluye importación y preprocesamiento de imágenes, equilibrado de datos, ajuste de hiperparámetros y entrenamiento del modelo.

## Descripción del Proyecto

El proyecto busca desarrollar un algoritmo de Machine Learning que pueda clasificar diferentes tipos de tumores de cuello uterino y sugerir el tratamiento más apropiado para cada caso. Se utiliza un conjunto de datos de imágenes de tumores proporcionadas por una competición en Kaggle lanzada por Intel y MobileODT. El enfoque se centra en la implementación de un modelo que pueda identificar y diferenciar entre tres tipos de tumores de cuello uterino.

## Importación y Preprocesamiento de Imágenes

Las imágenes de los tres tipos de tumores se importan y se someten a un proceso de preprocesamiento antes de su uso en el entrenamiento del modelo. El preprocesamiento incluye:

1. Reescalado de las imágenes utilizando OpenCV.
2. Recorte para eliminar bordes no determinantes.
3. Conversión a niveles de gris.
4. Aplicación de una máscara de convolución laplaciana para resaltar áreas significativas.
5. Ecualización del histograma para mejorar los resultados.

## Equilibrado de Datos

Dado que el conjunto de datos puede estar desequilibrado en términos de la cantidad de muestras para cada tipo de tumor, se realiza un equilibrado para evitar un sesgo hacia clases mayoritarias. Esto se logra utilizando la técnica SMOTE-Tomek, que combina Synthetic Minority Over-sampling Technique (SMOTE) y la eliminación de enlaces Tomek. Esta técnica genera muestras sintéticas de la clase minoritaria y elimina muestras cercanas a la clase mayoritaria en el espacio de características.

## Ajuste de Hiperparámetros

Los modelos RandomForest, KNN y GradientBoosting son ajustados utilizando RandomizedSearchCV y GridSearchCV para encontrar los mejores hiperparámetros que maximicen la puntuación F1. La puntuación F1 se utiliza para evaluar el rendimiento del modelo en términos de precisión y recuperación en problemas de clasificación.

## Entrenamiento y Evaluación del Modelo

Se utilizan varios clasificadores, incluyendo RandomForest, KNN y GradientBoosting, junto con el modelo de apilamiento (StackingClassifier), para entrenar y evaluar el rendimiento del modelo en el conjunto de datos equilibrado. Se emplea validación cruzada para obtener estimaciones precisas del rendimiento del modelo.

## Predicción y Resultados

Una vez entrenado el modelo, se utiliza para predecir los tipos de tumores en un conjunto de datos de prueba. Las etiquetas predichas se almacenan en un DataFrame para su análisis. Además, se demuestra el rendimiento del modelo en imágenes adicionales proporcionadas por Kaggle que no se utilizaron durante el entrenamiento ni la prueba.

## Conclusión

El proyecto muestra el desarrollo y entrenamiento de un algoritmo de Machine Learning capaz de clasificar tipos de tumores de cuello uterino y sugerir tratamientos adecuados en función de imágenes médicas. El enfoque incluye preprocesamiento de imágenes, equilibrado de datos, ajuste de hiperparámetros y entrenamiento de modelos, culminando en la capacidad de predecir tipos de tumores en datos de prueba y mostrar ejemplos adicionales para demostrar su desempeño. El resultado es un modelo que podría ser útil en la asistencia médica en la toma de decisiones clínicas para el tratamiento de tumores de cuello uterino.
