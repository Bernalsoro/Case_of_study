# Case_of_study
 Google Analitycs Coursera

1. ¿Cuáles son algunas tendencias en el uso de dispositivos inteligentes?
2. ¿Cómo podrían aplicarse estas tendencias a los clientes de Bellabeat?
3. ¿Cómo podrían influir estas tendencias en la estrategia de marketing de Bellabeat?

## Introducción
Caso de estudio de mi curso de Google Analytics. Supuesto práctico para poner aplicar lo aprendido en el curso.

1. Un resumen claro de la tarea empresarial

## Tarea empresarial:

Se le ha pedido que se centre en uno de los productos de Bellabeat y analice los datos de los dispositivos inteligentes para conocer cómo los utilizan los consumidores. La información que descubra ayudará a orientar la estrategia de marketing de la empresa. 

> Bellabeat: Un fabricante de alta tecnología que recopila datos sobre actividad, sueño y estrés para dotar a las mujeres de conocimientos sobre su propia salud y sus hábitos.

   
## Data
- Fuente: Data pública de [Kaggle](https://www.kaggle.com/arashnic)
- El conjunto de datos fue publicado por Möbius en Kaggle.com con la licencia CC0: Public Domain Creative Common License, que renuncia a todos los derechos sobre la obra y permite copiar, modificar, distribuir y ejecutar el conjunto de datos sin pedir permiso. Möbius citó el conjunto de datos de Zendo:Furberg, Robert; Brinton, Julia; Keating, Michael ; Ortiz, Alexa [Licencia](https://zenodo.org/record/53894#.ZBi8sOzMK3K)
- Esta base de datos fueron generados en una encuesta distribuida a través de Amazon Mechanical Turk entre el 04.12.2016-05.12.2016. 30 usuarios elegibles de Fitbit dieron su consentimiento para el envío de datos de rastreadores personales, incluidos los resultados minuto a minuto de la actividad física, la frecuencia cardíaca y la monitorización del sueño.
- La base de datos contiene 18 archivos.csv

### Organización de los datos
Se descargaron dieciocho conjuntos de datos de FitBit Fitness Tracker Data. Los datos  se descargaron en formato .csv e incluían formatos largos y anchos. Las bases de datos incluían un recuento de usuarios de 33 participantes durante un periodo de tiempo de 31 días.

2. Una descripción de todas las fuentes de datos utilizadas
3. Documentación de cualquier limpieza o manipulación de los datos
4. Un resumen de su análisis
5. Visualizaciones de apoyo y conclusiones clave
6. Recomendaciones de contenido de alto nivel basadas en su análisis

## Procesamiento de datos

He seleccionado los siguientes archivos.csv para mi análisis basándome en los criterios de peso de la base de datos e información más relevante.

- Daily_Activity_Merged
- Hourly_Steps_Merged
- Weight_Log_info_Merged
- Hourly_Calories_Merged
- Hourly_Intensity_Merged
- Daily_Sleep_Merged
- Heart_Rate_Merged

### Limpieza de las bases de datos

Comencé la limpieza de las bases de datos usando la aplicación Google Sheets. 

1. Ordenar y filtrar la columna de ID para saber cuantos valores únicos tiene.
2. Usar la opción de eliminar duplicados de google Sheets para detectar líneas de datos repetidas erróneamente.

Weight_log_info_merged:

1. Ordenar la base de datos por la columna del ID.
2. Usar la función de eliminar duplicados. (No hay duplicados encontrados)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.
5. Para corregir los datos de KG introducidos en formatos inconsistentes que podría dar error realizamos la siguiente consecución de funciones.
6. Convertimos los valores a texto con la función =TEXTO, extraemos solo los 4 primeros valores para redondear todos los datos al mismo formato (62,45KG) y arreglamos manualmente los diversos errores de formato consecuentes.
7. Para la columna de peso en Pounds convertimos los datos trabajados de Kg para convertirlos en Pounds =CONVERTIR(E3;"kg";"lbm"). Seguido de la función =IZQUIERDA(E3;5) para sacar solo los dígitos que queremos para redondear el peso.
8. Para calcular el IMC realizamos un proceso similar a los anteriores pero finalizando con una /100 para obtener decimales.
9. Eliminamos la columna "Fat" porque solo tiene dos filas con información. No nos aporta nada en el analisis.

[Doc] (https://docs.google.com/spreadsheets/d/1w-dmdM5tiXAt6Jq-CHu_ymobib3WQwBMTIt06UCdWcs/edit?usp=sharing)

sleep_day_merged:

1. Ordenar la base de datos por la columna del ID.
2. Usar función de elminar duplicados (3 filas eliminadas)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.

[Doc] (https://docs.google.com/spreadsheets/d/1YVixw0KGUk9Bhp07sh62YlOAgdGaErySShuXxLkl0QE/edit?usp=sharing)


daily_activity_merged:

1. Ordenar la base de datos por la columna del ID.
2. Usar la función de eliminar duplicados. (No hay duplicados encontrados)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Eliminar la columna Tracker distance por que tiene la misma info que totaldistance.
5. Elmininamos la columna LoggedActivitiesDistances por falta de info en la columna. Pocas filas completas.
6. Eliminamos la columna SedentaryActiveDistance por datos incorrectos y sin sentido.
7. Adaptado el formato en kilometros para la siguientes columnas VeryActiveDistance, ModeratelyActiveDistance y	LightActiveDistance.

[Doc](https://docs.google.com/spreadsheets/d/1It0i4vWwGqjK37p11CdaWbLDqMFPt53c3y5CFf07jJ4/edit?usp=sharing)







RECALCAR AL FINAL NOMBRES ESTANDARIZADOS Y NOMBRES DE COLUMMNAS
