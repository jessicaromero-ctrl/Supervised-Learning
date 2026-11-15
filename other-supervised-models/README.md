# Experimentos complementarios de aprendizaje supervisado

Índice de experimentos que complementan el proyecto principal de radiografías. Cada carpeta contiene su propio README con objetivo, protocolo, estado de resultados y pendientes.

| Carpeta | Algoritmo | Dataset | Estado |
|---|---|---|---|
| [clasificacion-supervisada](clasificacion-supervisada/README.md) | Seis algoritmos (LR, KNN, SVM, NB, árbol, bosque) | Digits, clasificación binaria | Documentado, sin resultados verificados |
| [decision-trees-cancerdb](decision-trees-cancerdb/README.md) | Árbol de decisión | Breast Cancer Wisconsin | Documentado, sin resultados verificados |
| [random-forest-cancerdb](random-forest-cancerdb/README.md) | Random Forest (10 árboles) | Breast Cancer Wisconsin | Documentado, sin resultados verificados |
| [gaussian-naive-bayes](gaussian-naive-bayes/README.md) | Gaussian Naive Bayes | Breast Cancer Wisconsin | Documentado, sin resultados verificados |
| [comp-pred](comp-pred/README.md) | Regresión lineal múltiple (OLS) | Precios de computadoras | Documentado en su README original |

## Notas transversales

- Los scripts de cáncer usan la clase `benign` como clase positiva. Las métricas de sensibilidad de esos scripts se refieren a benignos.
- Las particiones de los scripts de cáncer no fijan semilla, por lo que sus resultados no son reproducibles.
- `comp-pred/comp_pred.py` lee un CSV desde un repositorio externo y usa `statsmodels`, que no está en `requirements.txt`.
