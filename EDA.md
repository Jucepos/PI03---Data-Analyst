# Análisis Exploratorio de Datos (EDA). 

En este informe encontraremos de forma narrada la normalizacion nuestros datos para luego analizarlos. Cabe destacar que todos los cambios realizados en las tablas fueron hechos con PowerQuery, además, estas decisiones se basaron en utilizar las tablas y columnas que nos servian para cumplir con nuestro cliente a fin de poder mostrarle los datos mas certeros posibles que sirvan para su posterior toma de decisiones. Se analizo de acuerdo al interes en internet a traves de fibra optica y Tv paga.

## Objetivos de un EDA:

+ Maximizar el número de insights que obtenemos del dataset

+ Descubrir la estructura y las relaciones entre los datos

+ Extraer variables relevantes

+ Detectar anomalías, valores duplicados y valores perdidos (missing values)

+ Validar suposiciones o presuposiciones que podamos tener sobre los datos

+ Determinar la relevancia de los datos y optimizar el input de nuestros modelos

## Pasos de un EDA:

+ Carga de los datos

+ Limpieza de datos
                            
+ Visualización

## Datasets seleccionados:

+ Penetración de Internet fijo (accesos por cada 100 hogares.

+ Acceso a Internet fijo por tecnología y provincia.
 
+ Acceso a Internet Fijo por rangos de velocidad de bajada y provincia.
 
+ Penetración provincial de la televisión por suscripción (cada 100 hogares).
 
+ Total del país. Total de viviendas por provincia. Año 2010 (indec 2010).


## Importación a PowerBI y Normalización:

Primero que se realizo fue cargar los datasets descargados como csv para poder analizarlos y realizar las modificaciones con Power Query.

Analizamos que no surjan errores en la carga de los datasets.

Algunas columnas presentaban distinto tipos de datos (ej. estaban en formato text y se las transformo a formato numerico).

Pasamos a analizar cada tabla y ver la presencia o no de valores nulos y valores duplicados. En este caso ningún dataset tenia problema en este apartado.

Asimismo en el dataset de Acceso a internet Fijo por rangos de velocidad de bajada y provincia hubo que modificar algunos años que figuraban como 2019 *, para cambiarlos a solo 2019; lo mismo con el numero de trimestre (ej. 1 * por 1)

Creamos una columna con formato date a partir de la columna año y trimestre: Date= DATE([Año], SWITCH( [Trimestre], 1, 1, 2, 4, 3, 7, 4, 10) , 1).

Utilizamos merge query para unir todas las columnas que no se repetían e íbamos a utilizar para realizar las distintas métricas a través de las columnas Provincia, Año y Trimestre las cuales se presentaban en todos los datasets.

Una vez obtenida esta tabla con todos los datos, se inicio con el proceso de crear nuevas medidas y la creación de los graficos de visualizacion
