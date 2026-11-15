# Random Forest sobre Breast Cancer Wisconsin

## Objetivo

Clasificar las muestras del dataset Breast Cancer Wisconsin con un bosque aleatorio y reportar sus métricas.

## Dataset

- **Fuente:** `sklearn.datasets.load_breast_cancer`, con 569 muestras y 30 atributos numéricos.
- **Clases:** `malignant` (código 0, 212 muestras) y `benign` (código 1, 357 muestras).

## Interpretación de la clase positiva

Las métricas de precision, recall y F1 usan `pos_label=1` por defecto, que corresponde a **benigno**. El "recall" impreso por el script es la sensibilidad para casos benignos. Para evaluar la detección de casos malignos, debe usarse `pos_label=0`. El script no lo calcula.

## Protocolo

- **Partición:** 80 % entrenamiento y 20 % prueba, sin `random_state` ni estratificación.
- **Escalado:** `StandardScaler` ajustado solo con el conjunto de entrenamiento.
- **Modelo:** `RandomForestClassifier(n_estimators=10)`, sin semilla. Con 10 árboles, la variabilidad entre ejecuciones es alta.
- **Métricas:** matriz de confusión, precision, accuracy, recall, F1 y ROC AUC con probabilidades.
- **Gráficas:** visualización de uno de los árboles del bosque y curva ROC. El título de la curva dice "Regresión Logística", y debe corregirse.

## Estado de los resultados

Este README no incluye cifras. Los valores escritos como texto en el notebook original no se han verificado.

## Ejecución

```bash
cd other-supervised-models/random-forest-cancerdb
python randomforest_cancerdb.py
```

## Pendientes

1. Fijar `random_state` y usar `stratify`.
2. Aumentar `n_estimators` o justificar el valor 10.
3. Calcular el recall de la clase maligna (`pos_label=0`).
4. Corregir el título de la curva ROC y eliminar importaciones no usadas (`SVC`, `GaussianNB`, `DecisionTreeClassifier`).
