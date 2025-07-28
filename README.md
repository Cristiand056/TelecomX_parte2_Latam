# *TelecomX_parte2_Latam*
## En construción



## **Interpretación y conclusiones**
Según los resultados y pruebas, se llegaron a las siguientes conclusiones

El modelo seleccionado que bajo mi criterio se ajustó mejor a los requerimientos fue el modelo random forest, a pesar de que la variable objetivo está desbalanceada 74.6% en "Churn=0" y 26.4% "Churn=1".
Al ser un modelo no lineal, se mantuvieron todas las columnas, se tuvieron en cuenta las variables redundantes, que fueron evidenciadas por la correlación, que al retirarlas no fueron concluyentes en el modelo, por lo cual se dejaron.
Se probó el modelo con los balanceos SMOTE, NearMiss, con riguridad y dos pruebas de baja riguridad con SMOTEEN y SMOTETomek, usando un Pipeline, con el medoto cross validation, que me permitio elegir el balanceo que más sé acerba con los parametos elegidos fue el SMOTE.
Se usó la curva ROC para ver el rendimiento del modelo.
Con los datos, se decidio que era más importante priorizar los verdaderos positivos(Churn predicto = 1 y Churn real = 1), como todo fue necesario sacrificar la identificacion de falsos positivos (Churn predicto = 1 y Churn real = 0), para evitar la perdida de clientes y asegurar la retención de clientes que tengan un riesgo de abandonar.
Ya con una data frame sintetico de 6 ejemplos, se probó el modelo resultante, demostrando un comportamiento óptimo respecto a lo que se buscó, con mucho defice mostrado en su matriz de confución. [2 1] [1 2]
Pero de manera empirica el modelo se comporta mejor con los parametro originales dando una matriz de confución [2 1] [0 3]
el modelo de mejor rendimiento es guardo, para su posterior uso.
Se evidenció que el parametro R2 al ajustar los parametros con GridSearch, el R2 disminuye bastante.
