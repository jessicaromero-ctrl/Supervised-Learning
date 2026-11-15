# Gaussian Naive Bayes sobre Breast Cancer Wisconsin

## Objetivo

Clasificar las muestras del dataset Breast Cancer Wisconsin con un clasificador Naive Bayes gaussiano y reportar sus métricas.

## Dataset

- **Fuente:** `sklearn.datasets.load_breast_cancer`, con 569 muestras y 30 atributos numéricos.
- **Clases:** `malignant` (código 0, 212 muestras) y `benign` (código 1, 357 muestras).

## Interpretación de la clase positiva

Las métricas de precision, recall y F1 usan `pos_label=1` por defecto, que corresponde a **benigno**. Por tanto, la sensibilidad reportada corresponde a casos benignos. Para evaluar la detección de casos malignos, debe usarse `pos_label=0`. El script no lo calcula.

## Protocolo

- **Partición:** 80 % entrenamiento y 20 % prueba, sin `random_state` ni estratificación.
- **Escalado:** `StandardScaler` ajustado solo con el conjunto de entrenamiento. Para un modelo gaussiano por atributo, el escalado no cambia las predicciones de forma relevante, salvo por el término `var_smoothing`.
- **Modelo:** `GaussianNB()` con parámetros por defecto.
- **Métricas:** matriz de confusión, precision, accuracy, recall, F1 y ROC AUC con probabilidades.
- **Gráfica:** curva ROC. Su título dice "Regresión Logística" y debe corregirse.

## Estado de los resultados

Este README no incluye cifras. Los comentarios del notebook original con valores numéricos y su interpretación no se han verificado.

## Ejecución

```bash
cd other-supervised-models/gaussian-naive-bayes
python gaussiannb.py
```

## Pendientes

1. Fijar `random_state` y usar `stratify`. Aunque `GaussianNB` es determinista, la partición sí cambia los resultados.
2. Calcular el recall de la clase maligna (`pos_label=0`).
3. Corregir el título de la gráfica y eliminar `print(dataset)`.
