# Clasificación supervisada: comparación de seis algoritmos sobre Digits

## Objetivo

Comparar seis algoritmos de clasificación binaria sobre el dataset `load_digits` de scikit-learn. La tarea consiste en identificar el dígito 3 frente al resto de los dígitos.

## Dataset

- **Fuente:** `sklearn.datasets.load_digits`, imágenes de 8 × 8 píxeles con 64 atributos. Los valores van de 0 a 16.
- **Clase positiva:** dígito 3 (`y = 1`). Resto de dígitos (`y = 0`).
- **Partición:** 80 % entrenamiento y 20 % prueba, estratificada, con `random_state=42`.
- **Preprocesamiento:** ninguno. Los atributos se usan en su escala original.

## Modelos

| Modelo | Configuración |
|---|---|
| Logistic Regression | `max_iter=1000`, `random_state=42` |
| KNN | `n_neighbors=5` |
| SVM | kernel RBF, `probability=True`, `random_state=42` |
| Naive Bayes | `GaussianNB` con parámetros por defecto |
| Decision Tree | `max_depth=5`, `random_state=42` |
| Random Forest | `n_estimators=100`, `random_state=42` |

## Protocolo de evaluación

- **Conjunto de prueba:** accuracy, precision, recall y F1 con promedio ponderado (`classification_report`), y ROC AUC.
- **Validación cruzada:** 5 pliegues sobre el conjunto completo, con ROC AUC.
- **Salidas:** dashboard con curvas ROC, comparativa de AUC, matrices de confusión y resumen tabular.

## Estado de los resultados

Este README no incluye cifras. El script no se ha reejecutado de forma verificada en este repositorio. Las métricas se incorporarán después de la ejecución.

## Ejecución

```bash
cd other-supervised-models/clasificacion-supervisada
python clasificacion_supervisada.py
```

Requiere `numpy`, `matplotlib` y `scikit-learn`, incluidos en `requirements.txt` de la raíz.

## Pendientes

1. La ruta de guardado del dashboard (`/mnt/user-data/outputs/`) pertenece a otro entorno. Debe reemplazarse por una ruta relativa.
2. Agregar `StandardScaler` o justificar su ausencia para Logistic Regression, KNN y SVM.
3. Ejecutar el script y registrar las métricas en este README.
