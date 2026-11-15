# Supervised Learning: Portafolio de Aprendizaje Supervisado

Repositorio con dos bloques de trabajo: un pipeline de clasificación multiclase de radiografías torácicas (COVID-19, Neumonía, Normal) y un conjunto de experimentos complementarios de aprendizaje supervisado.

Maestría en Inteligencia Artificial · Universidad Politécnica Metropolitana de Hidalgo

## Proyectos

| Proyecto | Descripción | Documentación |
|---|---|---|
| Clasificación de radiografías respiratorias | Comparación de 8 algoritmos (deep learning y ML clásico) sobre 3,141 imágenes | [chest-xray-classification](chest-xray-classification/README.md) |
| Experimentos complementarios | Árboles de decisión, bosques aleatorios, Naive Bayes, análisis de precios | [other-supervised-models](other-supervised-models/README.md) |

## Resultados destacados (conjunto de prueba, 472 imágenes)

| Modelo | Accuracy | AUC-ROC |
|---|---|---|
| YOLOv8-cls | 0.9767 | 0.9980 |
| ResNet50 (transfer learning) | 0.9746 | 0.9973 |
| MLP | 0.9682 | 0.9930 |

Las cifras completas, incluido el desempeño por clase, están en el [README del proyecto de radiografías](chest-xray-classification/README.md).

## Estructura

```text
Supervised-Learning/
├── README.md
├── requirements.txt
├── .gitignore
├── chest-xray-classification/
│   ├── README.md
│   ├── notebooks/
│   ├── src/
│   ├── reports/
│   └── models/
└── other-supervised-models/
    ├── README.md
    └── comp_pred/
```

## Reproducibilidad

- Semilla fija `SEED = 42` en todos los procesos aleatorios.
- Las dependencias con versiones fijadas se encuentran en `requirements.txt`.
- El dataset no se incluye en el repositorio. Su ruta se configurará mediante variables de entorno en una fase posterior.
- Los pesos entrenados (`.keras`, `.pkl`, `.pt`) se excluyen por tamaño.
