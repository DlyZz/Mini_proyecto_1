# Proyecto Integrador — Predicción de Default en Préstamos
### Lending Club Loan Data · scikit-learn vs PySpark · Interpretabilidad con LIME

---

## Introducción

El presente proyecto tiene como objetivo desarrollar un modelo de clasificación binaria capaz de predecir si un préstamo otorgado a través de la plataforma Lending Club resultará en incumplimiento de pago (*Charged Off*) o será cancelado en su totalidad (*Fully Paid*). Para ello se utilizó el dataset público disponible en Kaggle, que comprende registros de préstamos emitidos entre 2007 y 2018, con aproximadamente 1,3 millones de observaciones y más de 150 variables financieras y demográficas.

El flujo de trabajo se estructuró en tres etapas principales. En primer lugar, se realizó un análisis exploratorio de datos (EDA) orientado a comprender la distribución de las variables, identificar valores faltantes y seleccionar las características más relevantes para el modelado. En segundo lugar, se implementaron dos pipelines de preprocesamiento y entrenamiento en paralelo: uno con **scikit-learn**, orientado a entornos de cómputo local, y otro con **PySpark**, pensado para escenarios de procesamiento distribuido a gran escala. Ambos pipelines entrenaron un clasificador **Random Forest** sobre una muestra de 500 000 registros, siguiendo las mismas combinaciones de hiperparámetros para garantizar la comparabilidad de resultados. Finalmente, se aplicó **LIME** (*Local Interpretable Model-agnostic Explanations*) para generar explicaciones individuales sobre las predicciones del modelo, con énfasis en los errores de clasificación más costosos desde la perspectiva financiera.

La métrica principal de evaluación es el **Recall**, dado que en el contexto de riesgo crediticio el error más grave es el Falso Negativo: predecir que un cliente pagará cuando en realidad incurrirá en default, lo que representa una pérdida directa del capital prestado para la institución financiera.
