# Case of study
## Google Analitycs Coursera

1. ¿Cuáles son algunas de las tendencias en el uso de dispositivos inteligentes?
2. ¿Cómo podrían aplicarse estas tendencias a los clientes de Bellabeat?
3. ¿Cómo podrían influir estas tendencias en la estrategia de marketing de Bellabeat?

## Introducción

Caso de estudio - Google Analytics / Coursera. Ejercicio práctico para aplicar los conocimientos adquiridos durante el curso.

## Tarea empresarial:

Se me ha asignado la tarea de centrarme en uno de los productos de Bellabeat y realizar un análisis de los datos provenientes de algunos dispositivos inteligentes. El objetivo es comprender cómo los consumidores están utilizando estos dispositivos, y la información recopilada será fundamental para orientar la estrategia de marketing.

> Bellabeat: Un fabricante de alta tecnología que recopila datos sobre actividad, sueño y estrés para dotar a las mujeres de conocimientos sobre su propia salud y sus hábitos.

   
## Data

- Fuente: Data pública de [Kaggle](https://www.kaggle.com/arashnic)
-El conjunto de datos fue publicado por Möbius en Kaggle.com con la licencia CC0: Public Domain Creative Common License, que renuncia a todos los derechos sobre la obra y permite copiar, modificar, distribuir y ejecutar el conjunto de datos sin pedir permiso. Möbius citó el conjunto de datos de Zendo:Furberg, Robert; Brinton, Julia; Keating, Michael ; Ortiz, Alexa [Licencia](https://zenodo.org/record/53894#.ZBi8sOzMK3K)
- Esta base de datos fueron generados en una encuesta distribuida a través de **Amazon Mechanical Turk** entre el **04.12.2016-05.12.2016.** 30 usuarios elegibles de Fitbit dieron su consentimiento para el envío de datos de rastreadores personales, incluidos los resultados minuto a minuto de la actividad física, la frecuencia cardíaca y la monitorización del sueño.
- La base de datos contiene **18 archivos.csv**

## Organización de los datos

Descargué dieciocho conjuntos de datos de FitBit Fitness Tracker Data. Los datos se descargaron en formato .csv e incluían formatos largos y anchos. Las bases de datos incluían un recuento de usuarios de 33 participantes durante un periodo de tiempo de 31 días.

## Procesamiento de datos

Seleccioné los siguientes archivos .csv para mi análisis basándome en los criterios de peso de la base de datos e información más relevante.

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
4. Crear una nueva columna para separar la hora de la fecha con la función "convertir texto en columna".
5. Para corregir posibles errores debido a los formatos inconsistentes de los datos de KG, seguimos la siguiente secuencia de funciones.
6. Convertimos los valores a texto mediante la función =TEXTO, extraemos solo los primeros cuatro caracteres para estandarizar el formato (62,45KG) y corregimos manualmente los posibles errores de formato.
7. Para la columna de peso en libras, convertimos los datos previamente procesados de kg utilizando la función =CONVERTIR(E3;"kg";"lbm"). Luego, aplicamos la función =IZQUIERDA(E3;5) para extraer solo los dígitos deseados y redondear el peso.
8. Para calcular el IMC realizamos un proceso similar a los anteriores pero finalizando con una /100 para obtener decimales.
9. Eliminamos la columna "Fat" porque solo tiene dos filas con información. No nos aporta nada en el analisis.

[Google Sheets](https://docs.google.com/spreadsheets/d/1w-dmdM5tiXAt6Jq-CHu_ymobib3WQwBMTIt06UCdWcs/edit?usp=sharing)

### sleep_day_merged:

1. Ordenar la base de datos por la columna "ID".
2. Usar la función "eliminar duplicados" (3 filas eliminadas)
3. Ordenar por fecha para comprobar si son datos del rango necesario.
4. Crear una nueva columna para separar la hora de la fecha utilizando la función "Convertir Texto en Columna".

[Google Sheets](https://docs.google.com/spreadsheets/d/1YVixw0KGUk9Bhp07sh62YlOAgdGaErySShuXxLkl0QE/edit?usp=sharing)


### daily_activity_merged:

1. Ordenar la base de datos por la columna "ID".
2. Usar la función "eliminar duplicados". (No hay duplicados encontrados)
3. Ordenar por fecha para comprobar si son datos del rango necesario.
4. Crear una nueva columna para separar la hora de la fecha utilizando la función "Convertir Texto en Columna".
5. Eliminar la columna 'Tracker distance' debido a que contiene la misma información que 'totaldistance'.
6. Eliminamos la columna 'LoggedActivitiesDistances' debido a la escasez de información en esa columna, con pocas filas completas.
7. Posteriormente, procedemos a eliminar la columna 'SedentaryActiveDistance' debido a la presencia de datos incorrectos y sin sentido.
8. Ajustamos el formato a kilómetros para las siguientes columnas: 'VeryActiveDistance', 'ModeratelyActiveDistance' y 'LightActiveDistance'.

[Google Sheets](https://docs.google.com/spreadsheets/d/1It0i4vWwGqjK37p11CdaWbLDqMFPt53c3y5CFf07jJ4/edit?usp=sharing)

### hourly_steps_merged:

1. Ordenar la base de datos por la columna "ID".
2. Usar la función "eliminar duplicados". (No hay duplicados encontrados)
3. Ordenar por fecha para comprobar si son datos del rango necesario.
4. Crear una nueva columna para separar la hora de la fecha utilizando la función "Convertir Texto en Columna".

[Google Sheets](https://docs.google.com/spreadsheets/d/16Q4W-bv156F_FrUtitflACY8NORWa0ZoYp-xh-GhGtA/edit?usp=sharing)

### hourly_caloriers_merged

1. Ordenar la base de datos por la columna "ID".
2. Usar la función "eliminar duplicados". (No hay duplicados encontrados)
3. Ordenar por fecha para comprobar si son datos del rango necesario.
4. Crear una nueva columna para separar la hora de la fecha utilizando la función "Convertir Texto en Columna".

[Google Sheets](https://docs.google.com/spreadsheets/d/1QYdGoyIUP4wgcX4TqDzuoPd3EnjPtZxW50ZnqOV7evw/edit?usp=sharing)

### AverageIntensity:

1. Ordenar la base de datos por la columna "ID".
2. Usar la función "eliminar duplicados". (No hay duplicados encontrados)
3. Ordenar por fecha para comprobar si son datos del rango necesario.
4. Crear una nueva columna para separar la hora de la fecha utilizando la función "Convertir Texto en Columna".
5. Modificar el formato de las columnas de tiempo y formatear correctamente la columna de intensidad.


[Google Sheets](https://docs.google.com/spreadsheets/d/1UM1kbPFeT6q5_903Kkuu4PfYj1uN_nvYTWkdGgUHc8o/edit?usp=sharing)


Hemos estandarizado tanto los nombres como el orden de las columnas para facilitar un análisis más efectivo en la plataforma **Big Query**.

## Fase de análisis y representación gráfica.

Para iniciar el análisis, evalué la utilidad de estas bases de datos mediante la verificación del número de usuarios únicos en cada tabla utilizando el siguiente código:

`SELECT COUNT(DISTINCT Id) AS Total_Id
FROM decisive-studio-380411.Bellabeat_case.daily_activity_merged `

Realicé la misma búsqueda con cada uno de los seis archivos seleccionados, ajustando la cláusula FROM para cada tabla correspondiente.

### Resultados:

- Daily_activity_merged: 33
- Hourly_calories_merged: 33
- Hourly_intensities_merged: 33
- hourly_steps_merged: 33
- sleep_day_merged: 24
- weight_log_merged: 8

La mayoría de las tablas contienen 33 IDs únicos, como mencioné al inicio del proyecto, pero hay dos tablas que contienen menos de lo estimado.

- En 'Sleep_day_merged', solo hay 24 IDs únicos, pero optaremos por utilizar esta información para el análisis por el momento.
- Weight_log_merged' cuenta únicamente con 8 IDs únicos, lo cual no es suficiente para extraer información, por lo que hemos decidido descartar esta tabla.

Basándome en la recomendación de pasos diarios realizada por **la universidad del Estado de Arizona, EEUU**, he segmentado a nuestros usuarios para extraer conclusiones.
[Estudio](https://pubmed.ncbi.nlm.nih.gov/14715035/)

Lo hicé con el siguiente **código**:

`SELECT AVG(TotalSteps)
FROM decisive-studio-380411.Bellabeat_case.daily_activity_merged
WHERE  Id =1503960366`

Cambié el número del Id para saber el promedio de cada usuario único.

Con el siguiente codigo descubrí los **ID únicos** de la tabla.

`SELECT DISTINCT ID
FROM decisive-studio-380411.Bellabeat_case.daily_activity_merged` 

Me ayudé del **formato condicional** y de **la funcion de google sheets  contar.si** para hacer un recuento y segmentación de estos datos.

[Google Sheets](https://docs.google.com/spreadsheets/d/1Od85SSWRcW4AML-0yNnlcNMJGiWnf0Q-IvRKoqXjbNM/edit?usp=sharing)


### Análisis pasos diarios.

Como podemos observar en el siguiente gráfico, los datos indican que no existe ninguna tendencia marcada hacia un estilo de vida específico entre nuestros usuarios; más bien, se aprecia una distribución equitativa.

![Recuento de Tipo de Actividad](https://user-images.githubusercontent.com/128240695/226921154-f0ab8b94-3f93-4cfb-a2ec-39ddb8c29663.png)

Otro estudio reciente realizando por Harvard Medical School afirma que las **tasas de mortalidad disminuyeron progresivamente** antes de nivelarse aproximadamente a los 7.500 pasos/día.

Por lo tanto, consideramos que ese es el mínimo recomendable.

[Estudio](https://jamanetwork.com/journals/jamainternalmedicine/fullarticle/2734709?guestAccessKey=afffe229-3940-4dd1-94e6-56cdd109c457&amp;utm_source=jps&amp;utm_medium=email&amp;utm_campaign=author_alert-jamanetwork&amp;utm_content=author-author_engagement&amp;utm_term=1m)

Podemos observar que hasta un **51,5%** de nuestros usuarios no llega a cumplir esos **7500 pasos diarios** que recomienda Harvard.

![Recuento Usuarios que cumplen la recomendación Harvard](https://user-images.githubusercontent.com/128240695/226929366-0e45012f-06a9-4571-8c55-533117124523.png)

### Análisis día de la semana

Pensé que sería una buena idea obtener la información de qué día de la semana corresponde a cada fecha. A continuación, explico el proceso realizado en Big Query para obtener esta información:

1. Creé una nueva columna en formato de texto (String) para almacenar esta información.

`Alter Table decisive-studio-380411.Bellabeat_case.daily_activity_merged
Add column Week_day String`

2. Para llenar esta columna recién creada con los días de la semana correspondientes a cada fila, utilicé el siguiente código:

`UPDATE decisive-studio-380411.Bellabeat_case.daily_activity_merged
SET Week_day = FORMAT_DATE('%A', Activity_date)
WHERE Activity_date IS NOT NULL`

3. A partir de esta nueva columna buscaré el promedio de pasos por día de la semana con el siguiente código:

`SELECT AVG(TotalSteps) 
FROMdecisive-studio-380411.Bellabeat_case.daily_activity_merged
WHERE Week_day = "Monday"`

Sustituí "Monday" por los distintos dias de la semana para obtener todos los resultados.

[Google Sheets](https://docs.google.com/spreadsheets/d/1KgOptSRCnpcnQJr4K4YyJ1kQO7JL5C2CE69bXhGdi1w/edit?usp=sharing)

Encontré una tendencia en los datos. 
El promedio de pasos diarios llega a la recomendación media de 7500 o se acerca mucho todos los días de la semana menos el domingo.

![Promedio de pasos por dia de la semana](https://user-images.githubusercontent.com/128240695/226968354-f912577c-9efd-480c-be1d-b2af9b641f39.png)

### Propuesta:

Propongo enviar una notificación un domingo al mes, avisando a nuestros usuarios de que ese día suele ser el menos activo para las personas. Sin ser invasivos, buscamos ayudar a nuestro cliente a alcanzar el objetivo por el cual compró nuestro producto: mejorar su salud.

### Analisis horas de sueño

Comencé un análisis más en profundidad de los parámetros relacionados con el sueño en nuestra base de datos. Decidimos crear también una columna para conocer los días de la semana correspondientes a estos datos, de manera similar a la realizada previamente.

1. Comencé creando una columna en formato texto para almacenar esta información con el siguiente código:

´Alter Table decisive-studio-380411.Bellabeat_case.sleep_day_merged
Add column Week_day String´

2. Incorporé la información del dia de la semana con el siguiente código:

`UPDATE decisive-studio-380411.Bellabeat_case.sleep_day_merged
SET Week_day = FORMAT_DATE('%A', Activity_date)
WHERE Activity_date IS NOT NULL`

A partir de las columnas "TotalTimeAtBed" y "TotalTimeAsleep". Mediante una resta entre estas dos columnas, obtuve los minutos que tarda en dormir cada usuario.
Usé el siguiente código para obtener el calculo e implementar esta información en la tabla.

1. Creé una tabla en formato INTEGER para obtener esta información en formato numérico.

`Alter Table decisive-studio-380411.Bellabeat_case.sleep_day_merged
Add Column Minutes_at_bed INTEGER`

2. Con el siguiente código obtuve esta operación actualizada en la base de datos.

`UPDATE decisive-studio-380411.Bellabeat_case.sleep_day_merged
SET Minutes_at_bed = TotalTimeInBed - TotalMinutesAsleep
WHERE TotalTimeInBed IS NOT NULL`

3. Junto al análisis de la columna creada "dias de la semana" y la función "AVERAGE"  encontré alguna tendencias en los resultados con el siguiente código:

`SELECT AVG(Minutes_at_bed) 
FROM decisive-studio-380411.Bellabeat_case.sleep_day_merged
WHERE Week_day = "Sunday"`

Igualmente sustituyendo este mismo código por cada dia de la semana y promedio general. 

[Google Sheets](https://docs.google.com/spreadsheets/d/1lbkMeb2SbFv39dUHy14dRMVVhlEBBdh2ta1xG3pknW0/edit?usp=sharing)

Como podemos observar en el siguiente gráfico se produce una subida de este tiempo en la cama para los fines de semana y sobretodo los Domingos.

![Promedio de minutos que tardan en dormirse cada dia de la semana](https://user-images.githubusercontent.com/128240695/226977785-3b8d7a1e-ee04-4560-bb16-7cc061321237.png)


#### Propuesta

Proponemos enviar notificaciónes al dispositivo recordando la importancia de un buen descanso e informando al propio usuario de sus habitos recurrentes insanos.

## Analisis de correlaciones

Nos parecio buena idea buscar correlaciones entre distintos valores para ver si encontrabamos indicios de alguna tendencia.

1. Creamos una nueva tabla en excel para un analisis más facil e intuitivo que también mejorara la calidad de las visualizaciones de datos que nos aporta la plataforma.
2. Ordenamos la base de datos por ID en orden ascendente de las siguientes tablas "Sleep_day_merged" y "Daily_Activity_Merged". Copiamos la columna de minutes_at_bed de "Sleep_day_merged" y las de TotalSteps y TotalCalories de la "Daily_Activity_Merged". 
3. Creamos un nuevo Google Sheets llamado "Correlation_Table". Y adjuntamos estas Tablas.      [Google Sheets](https://docs.google.com/spreadsheets/d/1nUWP_TwJ9dMgoFm_-OmHyNHDttduPXTgRsQVBBTms0g/edit?usp=sharing)
4. Obtuvimos las siguientes visualizaciones.

![Correlacion entre calorias quemadas y minutos que les cuesta dormir](https://user-images.githubusercontent.com/128240695/227176771-79928458-abeb-4a7f-b1cf-c592d12939cb.png)

![Correlación entre pasos totales y minutos que les cuesta dormir](https://user-images.githubusercontent.com/128240695/227176819-d7c65af8-2ff9-4450-ac4c-f2278fcbae94.png)

## Conclusión:

En ninguna de las dos visualizaciones vemos una tendencia marcada, ni causalidad.
Se puede interpretar una correlación a que la mayoría de usuarios que realiza los pasos diarios y la quema de calorias recomendada consigue dormirse en tiempos razonables. Sin embargo, también hay muchos usuarios que sin cumplir estos requerimientos se duermen en tiempos similares.

Con lo que entendemos que los minutos que le cuestan dormir a las personas es un tema multifactorial y que no existe una causalidad con la quema de calorias y los pasos dados.


## Análisis pasos totales por franja horaria:

Decidimos investigar a que horas era más común que caminaran nuestros usuarios.

Usamos la plataforma Google Sheets para realizar este analisis y visualización.

1. Usamos la tabla "Hourly_steps"
2. Filtrando por nuestra columna AM_PM podemos ayudar al sowftware a ofrecernos mejores visualizaciones y facilitar el analisis.
3. Obtenemos las siguientes visualizaciones:

![Media de pasos totales por franja horaria AM](https://user-images.githubusercontent.com/128240695/227185620-49b5cc03-d98f-49e7-b982-2093bcf09ec0.png)

![Media de pasos totales por franja horaria PM](https://user-images.githubusercontent.com/128240695/227185646-f6a04f20-4360-4294-a1e9-5bcdd01a717e.png)


**Franja horaria AM:**

Hora a la que más andan de media: 9:00 AM
Hora a la que menos andan de media: 3:00 AM

**Franja horaria PM** 

Hora a la que más andan de media: 14:00 PM  **Es la hora a la que más andan de todo el día en general**
Hora a la que menos andan de media: 20:00 PM

**Conclusión y sugerencia**

Estos datos muestran la medio de los horarios de caminar de nuestros clientes. Por lo tanto podríamos desarrollar campañas de marketing potenciando las horas a las que ya caminan nuestros clientes o intentando mejorar a las que no caminan.

Ejemplo: Si interpretamos que tanto a las 9:00 AM como a las 14:00 PM caminan tanto por que estan llendo o volviendo del trabajo podemos buscar incentivar a la gente que busque completar los pasos necesarios del día en estos momentos. Haciendo campañas para incentivar no usar el ascensor o medidas similares.


