# *TelecomX_parte2_Latam*
## En construción

## Conrexto inicial
¡Felicidades! 🎉 Has sido promovido después de tu excelente desempeño en el análisis exploratorio de la cancelación de clientes en Telecom X. Tu dedicación, claridad al comunicar los datos y visión estratégica marcaron la diferencia.

Ahora, ¡has sido invitado oficialmente a formar parte del equipo de Machine Learning de la empresa!

### Diccionario de datos
- customerID: número de identificación único de cada cliente
- Churn: si el cliente dejó o no la empresa
- gender: género (masculino y femenino)
- SeniorCitizen: información sobre si un cliente tiene o no una edad igual o mayor a 65 años
- Partner: si el cliente tiene o no una pareja
- Dependents: si el cliente tiene o no dependientes
- tenure: meses de contrato del cliente
- PhoneService: suscripción al servicio telefónico
- MultipleLines: suscripción a más de una línea telefónica
- InternetService: suscripción a un proveedor de internet
- OnlineSecurity: suscripción adicional de seguridad en línea
- OnlineBackup: suscripción adicional de respaldo en línea
- DeviceProtection: suscripción adicional de protección del dispositivo
- TechSupport: suscripción adicional de soporte técnico, menor tiempo de espera
- StreamingTV: suscripción de televisión por cable
- StreamingMovies: suscripción de streaming de películas
- Contract: tipo de contrato
- PaperlessBilling: si el cliente prefiere recibir la factura en línea
- PaymentMethod: forma de pago
- Charges.Monthly: total de todos los servicios del cliente por mes
- Charges.Total: total gastado por el cliente

## Resumen de la operación
1. Se importo el archivo con <b>Pandas</b>.
2. Se limpio el data frame por que se observaron datos vacios.
3. Se realizo la codificacion <b>one hot encoder</b>, para las columnas categóricas.
4. 

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
