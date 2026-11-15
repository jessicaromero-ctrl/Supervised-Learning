# Árbol de decisión sobre Breast Cancer Wisconsin

## Objetivo

Clasificar las muestras del dataset Breast Cancer Wisconsin con un árbol de decisión y reportar sus métricas de desempeño.

## Dataset

- **Fuente:** `sklearn.datasets.load_breast_cancer`, con 569 muestras y 30 atributos numéricos.
- **Clases:** `malignant` (código 0, 212 muestras) y `benign` (código 1, 357 muestras).

## Interpretación de la clase positiva

Las funciones `precision_score`, `recall_score` y `f1_score` usan `pos_label=1` por defecto. En este dataset, esa clase es **benigno**. Por tanto, el "recall" que imprime el script es la sensibilidad para detectar casos benignos, no malignos.

En un contexto de cribado, la métrica relevante es el recall de la clase maligna (`pos_label=0`). El script no la calcula. Para obtenerla, debe usarse `recall_score(y_test, y_pred, pos_label=0)`.

## Protocolo

- **Partición:** 80 % entrenamiento y 20 % prueba, sin `random_state` ni estratificación. Los resultados cambian entre ejecuciones.
- **Escalado:** `StandardScaler` ajustado solo con el conjunto de entrenamiento.
- **Modelo:** `DecisionTreeClassifier()` con parámetros por defecto, sin límite de profundidad.
- **Métricas:** matriz de confusión, accuracy, precision, recall, F1 y ROC AUC calculado con probabilidades.
- **Gráfica:** curva ROC. Su título dice "Regresión Logística", aunque el modelo es un árbol de decisión.

## Estado de los resultados

Este README no incluye cifras. Los valores escritos como texto en el notebook original no se han verificado y no se consideran resultados del proyecto.

## Ejecución

```bash
cd other-supervised-models/decision-trees-cancerdb
python decisiontrees_cancerdb.py
```

## Pendientes

1. Fijar `random_state` y usar `stratify` en la partición.
2. Calcular el recall de la clase maligna (`pos_label=0`).
3. Corregir el título de la gráfica.
4. Corregir `df.head` (sin paréntesis) y eliminar `print(dataset)`, que imprime el objeto completo.
