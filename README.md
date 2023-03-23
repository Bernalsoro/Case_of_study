# Case of study
## Google Analitycs Coursera

1. ¿Cuáles son algunas tendencias en el uso de dispositivos inteligentes?
2. ¿Cómo podrían aplicarse estas tendencias a los clientes de Bellabeat?
3. ¿Cómo podrían influir estas tendencias en la estrategia de marketing de Bellabeat?

## Introducción

Caso de estudio de mi curso de Google Analytics. Supuesto práctico para poner aplicar lo aprendido en el curso.

## Tarea empresarial:

Se nos ha pedido que nos centremos en uno de los productos de Bellabeat y analice los datos de los dispositivos inteligentes para conocer cómo los utilizan los consumidores. La información que descubra ayudará a orientar la estrategia de marketing de la empresa. 

> Bellabeat: Un fabricante de alta tecnología que recopila datos sobre actividad, sueño y estrés para dotar a las mujeres de conocimientos sobre su propia salud y sus hábitos.

   
## Data

- Fuente: Data pública de [Kaggle](https://www.kaggle.com/arashnic)
-El conjunto de datos fue publicado por Möbius en Kaggle.com con la licencia CC0: Public Domain Creative Common License, que renuncia a todos los derechos sobre la obra y permite copiar, modificar, distribuir y ejecutar el conjunto de datos sin pedir permiso. Möbius citó el conjunto de datos de Zendo:Furberg, Robert; Brinton, Julia; Keating, Michael ; Ortiz, Alexa [Licencia](https://zenodo.org/record/53894#.ZBi8sOzMK3K)
- Esta base de datos fueron generados en una encuesta distribuida a través de **Amazon Mechanical Turk** entre el **04.12.2016-05.12.2016.** 30 usuarios elegibles de Fitbit dieron su consentimiento para el envío de datos de rastreadores personales, incluidos los resultados minuto a minuto de la actividad física, la frecuencia cardíaca y la monitorización del sueño.
- La base de datos contiene **18 archivos.csv**

### Organización de los datos

Se descargaron dieciocho conjuntos de datos de FitBit Fitness Tracker Data. Los datos  se descargaron en formato .csv e incluían formatos largos y anchos. Las bases de datos incluían un recuento de usuarios de 33 participantes durante un periodo de tiempo de 31 días.

## Procesamiento de datos

He seleccionado los siguientes archivos.csv para mi análisis basándome en los criterios de peso de la base de datos e información más relevante.

#### - Daily_Activity_Merged
#### - Hourly_Steps_Merged
#### - Weight_Log_info_Merged
#### - Hourly_Calories_Merged
#### - Hourly_Intensity_Merged
#### - Daily_Sleep_Merged

## Limpieza de las bases de datos

Comencé la limpieza de las bases de datos usando la aplicación **Google Sheets**. 

1. Ordenar y filtrar la columna de ID para saber cuantos valores únicos tiene.
2. Usar la opción de eliminar duplicados de google Sheets para detectar líneas de datos repetidas erróneamente.

### Weight_log_info_merged:

1. Ordenar la base de datos por la columna del ID.
2. Usar la función de eliminar duplicados. (No hay duplicados encontrados)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.
5. Para corregir los datos de KG introducidos en formatos inconsistentes que podría dar error realizamos la siguiente consecución de funciones.
6. Convertimos los valores a texto con la función =TEXTO, extraemos solo los 4 primeros valores para redondear todos los datos al mismo formato (62,45KG) y arreglamos manualmente los diversos errores de formato consecuentes.
7. Para la columna de peso en Pounds convertimos los datos trabajados de Kg para convertirlos en Pounds =CONVERTIR(E3;"kg";"lbm"). Seguido de la función =IZQUIERDA(E3;5) para sacar solo los dígitos que queremos para redondear el peso.
8. Para calcular el IMC realizamos un proceso similar a los anteriores pero finalizando con una /100 para obtener decimales.
9. Eliminamos la columna "Fat" porque solo tiene dos filas con información. No nos aporta nada en el analisis.

[Google Sheets](https://docs.google.com/spreadsheets/d/1w-dmdM5tiXAt6Jq-CHu_ymobib3WQwBMTIt06UCdWcs/edit?usp=sharing)

### sleep_day_merged:

1. Ordenar la base de datos por la columna del ID.
2. Usar función de elminar duplicados (3 filas eliminadas)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.

[Google Sheets](https://docs.google.com/spreadsheets/d/1YVixw0KGUk9Bhp07sh62YlOAgdGaErySShuXxLkl0QE/edit?usp=sharing)


### daily_activity_merged:

1. Ordenar la base de datos por la columna del ID.
2. Usar la función de eliminar duplicados. (No hay duplicados encontrados)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.
5. Eliminar la columna Tracker distance por que tiene la misma info que totaldistance.
6. Elmininamos la columna LoggedActivitiesDistances por falta de info en la columna. Pocas filas completas.
7. Eliminamos la columna SedentaryActiveDistance por datos incorrectos y sin sentido.
8. Adaptado el formato en kilometros para la siguientes columnas VeryActiveDistance, ModeratelyActiveDistance y	LightActiveDistance.

[Google Sheets](https://docs.google.com/spreadsheets/d/1It0i4vWwGqjK37p11CdaWbLDqMFPt53c3y5CFf07jJ4/edit?usp=sharing)

### hourly_steps_merged:

1. Ordenar la base de datos por la columna del ID.
2. Usar la función de eliminar duplicados. (No hay duplicados encontrados)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.

[Google Sheets](https://docs.google.com/spreadsheets/d/16Q4W-bv156F_FrUtitflACY8NORWa0ZoYp-xh-GhGtA/edit?usp=sharing)

### hourly_caloriers_merged

1. Ordenar la base de datos por la columna del ID.
2. Usar la función de eliminar duplicados. (No hay duplicados encontrados)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.

[Google Sheets](https://docs.google.com/spreadsheets/d/1QYdGoyIUP4wgcX4TqDzuoPd3EnjPtZxW50ZnqOV7evw/edit?usp=sharing)

### AverageIntensity:

1. Ordenar la base de datos por la columna del ID.
2. Usar la función de eliminar duplicados. (No hay duplicados encontrados)
3. Ordenados por fecha para comprobar que aportan datos del rango supuesto.
4. Crear una nueva columna para separar la hora de la fecha con la función convertir texto en columna.
5. Cambiar de formato columnas de tiempo y formatear correctamente la columna de intensidad.


[Google Sheets](https://docs.google.com/spreadsheets/d/1UM1kbPFeT6q5_903Kkuu4PfYj1uN_nvYTWkdGgUHc8o/edit?usp=sharing)



Hemos realizado una estandarización de las columnas tanto de los nombres como del orden para poder realizar un mejor análisis en la plataforma **Big Query**.

## Fase de análisis y representación gráfica.

Para comenzar el análisis vamos a comprobar como de útiles son estas bases de datos comprobando cuantos usuarios únicos contiene cada tabla con el siguiente código:

`SELECT COUNT(DISTINCT Id) AS Total_Id
FROM decisive-studio-380411.Bellabeat_case.daily_activity_merged `

Realizaremos la misma busqueda con cada uno de los 6 archivos seleccionados adaptando el apartado FROM a cada tabla.

### Resultados:

- Daily_activity_merged: 33
- Hourly_calories_merged: 33
- Hourly_intensities_merged: 33
- hourly_steps_merged: 33
- sleep_day_merged: 24
- weight_log_merged: 8

La mayoría de tablas contienen 33 IDs únicos como se comentaba al inicio del proyecto pero hay dos que contienen menos de lo supuesto.

- Sleep_day_merged tiene solo 24 IDs únicos pero vamos a usar esta información para análisis de momento.
- Weight_log_merged solo tiene 8 IDs únicos y no nos es suficiente para sacar información por lo que decidimos descartar esta tabla.


Basandonos en la recomendación de pasos diarios realizada por **la universidad del Estado de Arizona, EEUU**. Segmentaremos a nuestros usuarios para sacar conclusiones

[Doc](https://pubmed.ncbi.nlm.nih.gov/14715035/)


Lo haremos con el siguiente **código**:

`SELECT AVG(TotalSteps)
FROM decisive-studio-380411.Bellabeat_case.daily_activity_merged
WHERE  Id =1503960366`

Cambiaremos el número del Id para saber el promedio de cada usuario único.

Nos ayudaremos del siguiente codigo para saber los **ID únicos** de la tabla.

`SELECT DISTINCT ID
FROM decisive-studio-380411.Bellabeat_case.daily_activity_merged` 

Nos ayudamos del **formato condicional** y de **la funcion de google sheets  contar.si** para hacer un recuento y segmentación de estos datos.

[Google Sheets](https://docs.google.com/spreadsheets/d/1Od85SSWRcW4AML-0yNnlcNMJGiWnf0Q-IvRKoqXjbNM/edit?usp=sharing)


### Análisis pasos diarios.

Como podemos observar en el siguiente gráfico los datos nos muestran que no existe ninguna tendencia marcada a llevar un estilo de vida entre nuestros usuarios si no que se ve un reparto equivalente.

![Recuento de Tipo de Actividad](https://user-images.githubusercontent.com/128240695/226921154-f0ab8b94-3f93-4cfb-a2ec-39ddb8c29663.png)

Otro estudio reciente realizando por Harvard Medical School afirma que las **tasas de mortalidad disminuyeron progresivamente** antes de nivelarse aproximadamente a los 7.500 pasos/día.

Por lo que consideramos que ese es el mínimo recomendable.

[Doc](https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/2734709?guestAccessKey=afffe229-3940-4dd1-94e6-56cdd109c457&amp;utm_source=jps&amp;utm_medium=email&amp;utm_campaign=author_alert-jamanetwork&amp;utm_content=author-author_engagement&amp;utm_term=1m)

Podemos observar que hasta un **51,5%** de nuestros usuarios no llega a cumplir esos **7500 pasos diarios** que recomienda Harvard

![Recuento Usuarios que cumplen la recomendación Harvard](https://user-images.githubusercontent.com/128240695/226929366-0e45012f-06a9-4571-8c55-533117124523.png)

### Análisis día de la semana
Pensamos que sería una buena idea obtener la información de que dia de la semana es cada fecha. Explico el proceso realizado en Big Query para obtener esta información:

1. Creamos una columna nueva en formato String en la que almacenaremos esta información en formato texto:


`Alter Table decisive-studio-380411.Bellabeat_case.daily_activity_merged
Add column Week_day String`

2. Para completar esta columna recien creada con los dias de la semana correspondiente a cada fila utilizaremos el siguiente codigo:

`UPDATE decisive-studio-380411.Bellabeat_case.daily_activity_merged
SET Week_day = FORMAT_DATE('%A', Activity_date)
WHERE Activity_date IS NOT NULL`

3. A partir de esta nueva columna realizamos buscaremos el promedio de pasos por dia de la semana con el siguiente código:

`SELECT AVG(TotalSteps) 
FROMdecisive-studio-380411.Bellabeat_case.daily_activity_merged
WHERE Week_day = "Monday"`

Sustituiremos "Monday" por los distintos dias de la semana para obtener todos los resultados.
[Google Sheets](https://docs.google.com/spreadsheets/d/1KgOptSRCnpcnQJr4K4YyJ1kQO7JL5C2CE69bXhGdi1w/edit?usp=sharing)

Observamos una tendencia en los datos. 
El promedio de pasos diarios llega a la recomendación media de 7500 o se acerca mucho todos los días de la semana menos el domingo.

![Promedio de pasos por dia de la semana](https://user-images.githubusercontent.com/128240695/226968354-f912577c-9efd-480c-be1d-b2af9b641f39.png)

#### Propuesta:
Propongo enviar una notificación un domingo al mes avisando a nuestros usuarios de que ese dia suele ser el más inactivo para la gente.
Sin ser invasivos pero buscando ayudar a nuestro cliente a perseguir el objetivo por el cual compro nuestro producto, tener una mejor salud.

### Analisis horas de sueño
Comenzando un analisis más en profundidad sobre los parametros sobre el sueño que existen en nuestra bases de datos decidimos crear también una columna para saber los dias de la semana de esta de manera similar a la previamente realizada.

1. Comenzamos creando una columna en formato texto para almacenar esta información con el siguiente código:

´Alter Table decisive-studio-380411.Bellabeat_case.sleep_day_merged
Add column Week_day String´

2. Incorporamos la información del dia de la semana con el siguiente código:

`UPDATE decisive-studio-380411.Bellabeat_case.sleep_day_merged
SET Week_day = FORMAT_DATE('%A', Activity_date)
WHERE Activity_date IS NOT NULL`

A partir de las columnas "TotalTimeAtBed" y "TotalTimeAsleep". Mediante una resta entre estas dos columnas buscamos obtener los minutos que le cuesta dormirse al usuario. Usaremos el siguiente código para obtener el calculo e implementar esta información en la tabla.

1. Creamos una tabla en formato INTEGER para obtener esta información en número.

`Alter Table decisive-studio-380411.Bellabeat_case.sleep_day_merged
Add Column Minutes_at_bed INTEGER`

2. Con el siguiente código obtenemos esta operación actualizada en la base de datos.

`UPDATE decisive-studio-380411.Bellabeat_case.sleep_day_merged
SET Minutes_at_bed = TotalTimeInBed - TotalMinutesAsleep
WHERE TotalTimeInBed IS NOT NULL`

3. Junto al analisis de la columna creada de dias de la semana y la función AVERAGE buscamos encontrar tendencias en los resultados con el siguiente codigo

`SELECT AVG(Minutes_at_bed) 
FROM decisive-studio-380411.Bellabeat_case.sleep_day_merged
WHERE Week_day = "Sunday"`

Igualmente sustituyendo este mismo código por cada dia de la semana y promedio general. 

[Google Sheets](https://docs.google.com/spreadsheets/d/1lbkMeb2SbFv39dUHy14dRMVVhlEBBdh2ta1xG3pknW0/edit?usp=sharing)

Como podemos observar en el siguiente gráfico se produce una subida de este tiempo en la cama para los fines de semana y sobretodo los Domingos.

![Promedio de minutos que tardan en dormirse cada dia de la semana](https://user-images.githubusercontent.com/128240695/226977785-3b8d7a1e-ee04-4560-bb16-7cc061321237.png)


#### Propuesta

Proponemos enviar notificaciónes al dispositivo recordando la importancia de un buen descanso e informando al propio usuario de sus habitos recurrentes insanos.






