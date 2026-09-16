# Portfolio de Machine Learning

Ocho proyectos que recorren el ciclo completo de un problema de datos: exploración, preprocesado, modelado, evaluación y explicabilidad. Todos los notebooks están ejecutados y con los resultados visibles.

Realizados durante el Curso de Especialización de FP en Inteligencia Artificial y Big Data (CIFP Carlos III, Cartagena).

## Contenido

| Notebook | Problema | Técnicas | Resultado |
|---|---|---|---|
| `01-eda-completo-diamantes` | Análisis exploratorio de 53.940 diamantes | Detección de nulos físicos, outliers por densidad (volumen/quilates), asimetría y curtosis, ingeniería de variables | Se detectan y justifican 20 registros imposibles y outliers de medición |
| `02-regresion-comparativa-modelos` | Predecir el precio de un automóvil (UCI Imports-85) | Pipelines de scikit-learn, regresión lineal, Ridge, polinómica, SVR, árbol, Random Forest, ensemble | Random Forest: **R² 0,932** en test. El ensemble de los 3 mejores baja algo más el error |
| `03-clasificacion-abandono-clientes` | Predecir la fuga de clientes de una teleco | Regresión logística, KNN, SVM, Naive Bayes, árbol, Random Forest, GridSearch | SVM lineal: **79,5 %** de acierto. El recall (0,47) evidencia el desbalance de clases |
| `04-clustering-y-anomalias-ciberseguridad` | Detección de intrusiones (KDD Cup 99) | K-Means, DBSCAN, propagación de afinidad, reglas de asociación, Isolation Forest | Isolation Forest: **recall 0,945** sobre el tráfico malicioso |
| `05-reduccion-dimensionalidad-riesgo-credito` | Riesgo de impago (German Credit) | Correlación, importancia de variables, ANOVA, RFE, PCA | **ROC AUC 0,799**, comparando el modelo completo contra el reducido |
| `06-xgboost-automl-y-shap` | Mejora de los modelos anteriores | XGBoost, PyCaret (AutoML), SHAP | XGBoost en regresión: **R² 0,949** (mejora el 0,932 anterior). Clasificación: ROC AUC 0,831 |
| `07-redes-neuronales-keras-tuner-spotify` | Popularidad y éxito comercial de canciones | Keras, búsqueda de hiperparámetros con KerasTuner | Clasificación: **ROC-AUC 0,833**. En regresión la red no supera a XGBoost, y se explica por qué |
| `08-redes-neuronales-keras-tuner-automoviles` | El mismo problema del notebook 02, con redes | Keras + KerasTuner, análisis de sobreajuste | **R² 0,918** en test, con la mejor época identificada |

## Criterio de trabajo

- La separación de entrenamiento y test se hace **antes** de cualquier ajuste, para evitar fugas de información.
- El sobreajuste se mide comparando el error de entrenamiento con el de test, y se analiza con gráficos de residuos.
- Cuando un modelo rinde peor, se documenta en vez de ocultarlo: el notebook 07 explica por qué una red neuronal no siempre gana.

## Cómo ejecutarlos

```bash
pip install -r requirements.txt
jupyter lab
```

Los datos se descargan desde el propio notebook (UCI, Kaggle o `seaborn`), así que no hace falta añadir ficheros.
