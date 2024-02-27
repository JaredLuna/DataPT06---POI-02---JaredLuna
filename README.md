# DataPT06---POI-02---JaredLuna
*Segundo proyecto individual de Henry, para la carrera de DataScience en PT Cohorte 06. *

Para este proyecto se nos plantea la siguiente problemática:

*"El Observatorio de Movilidad y Seguridad Vial (OMSV), centro de estudios que se encuentra bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires, nos solicita la elaboración de un proyecto de análisis de datos, con el fin de generar información que les permita a las autoridades locales tomar medidas para disminuir la cantidad de víctimas fatales de los siniestros viales."*

Dentro del mismo se nos plantean las maneras a trabajar. Como en el proyecto pasado primero se tiene que desarrollar la EDA, luego una ETL y finalmente (en este caso) el dashboard. Los datasets que se nos proporcionan estarán en la carpeta de *Datasets*.

Primeramente, comenzare a explicar cada una de las partes de dicho desarrollo, de los mimos modo todo lo que se fue generando y finalmente los resultados.

## EDA

Para la parte de la EDA primeramente se descargó el dataset con el que se empezó a trabajar. Dicho dataset se encuentra en la carpeta de **Datasets** y se llama "homicidios". En este dataset encontramos varios datos sobre accidentes en la CABA, venían particionados por ID, fechas, calles e involucrados. En ese dataset (que es un archivo CSV), contenía dos hojas, la de "hechos" y la de "victimas". Se extrajeron esas dos hojas para poder hacer una relación entre las víctimas y los involucrados en todos los accidentes, así como para tener un control de las fechas y horas de los accidentes.

Una vez que tuvimos identificadas nuestras hojas objetivo, se procedió a importarlas a dos archivos csv diferentes (uno para cada hoja). Estos archivos igualmente se encuentran en la carpeta de Datasets como:

- HechosEDA

- VictimasEDA

Estos serán los archivos con los que se trabajaron en Python para la EDA y la ETL.

Para el comienzo de la EDA primeramente se importaron los archivos CSV con los que íbamos a trabajar para poder visualizarlos. Para más detalle del paso a paso que se realizó en la EDA se puede abrir el archivo de *"EDA.ipynb"* que se encuentra dentro del folder de Notebooks. En esta inspección nos dimos cuenta de que contábamos con algunas columnas con datos faltantes, al ser varios valores así perderíamos mucha información en su eliminación por lo que se optó por reemplazar los datos faltantes por "SD", pero esto se realizó en la parte de la ETL. 

Una vez que revisamos toda la información, apuntamos los datos pertinentes como comentarios de Mark Down, se procedió a la transformación de nuestros datos en la parte de la ETL.

## ETL

Para esta parte volvimos a tomar los datos que tenemos en el folder de Datasets para trabajar con ellos. De la misma manera dentro del jupyter notebook se encuentran comentarios más detallados de lo realizado en la transformación de los datos. Fue una transformación sencilla, ya que solamente nos encargamos de reemplazar valores vacíos y separar fechas para tener un mejor control de tiempos. Realmente esta parte era opcional en el proyecto, pero para tener un dataset más ordenado se realizó esta pequeña limpieza.

Una vez terminada la transformación se guardaron los archivos en formato parquet, esto solo para tener unos archivos más livianos y trabajar con ellos en PowerBi.


## Dashboard en PowerBI

Para esta parte es donde se nos propusieron 2 KPI's más uno extra propuesto por nosotros. Los dos KPI's son:

- Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

- Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

Estos dos KPI's serán generados a partir de varias métricas que se encuentran o se han generado en el proyecto. Como en PowerBi es imposible poner comentarios sobre el proyecto es necesario hacer un poco más detallada esta parte del ReadMe.

### Importación de datos.

Como se mencionó en la parte de la ETL, se importaron los datos en formato parquet. Así que para PowerBi ya no hay problema para la lectura de los archivos, una vez importamos revisamos que estuvieran todos los datos bien importados, que no haya valores nulos ni ningún problema con los tipos de datos. Una vez revisado este se procedió a hacer el dashboard como tal.

### Páginas del dashboard.

Para la presentación de las páginas se optó por utilizar Power Point como ayuda para los fondos de nuestro dashboard. Para esto simplemente realizabas el arrastre de elementos en una hoja de PowerPoint común y corriente, una vez todos los elementos posicionados y con colocados de la manera deseada solo es cuestión de importar nuestro archivo en formato SVG, el cual es un formato que vectoriza la diapositiva para poder escalarla sin perder nada de calidad en la imagen.

Estas dispositivas se encuentran en el folder de *"Resources"* ya transformadas al formato SVG. 

Una vez listos los fondos de nuestro dashboard nos centramos en las métricas y los KPI's junto con el story telling de nuestro dashboard.

### KPI's.

Para los KPI's primeramente nos centramos en la tasa de homicidios, la cual fue calculada con la población esperada para el 2021. Este índice de población fue extraído de las proyecciones de población de la Ciudad Autónoma de Buenos Aires. La cual en su análisis destaca que para el año 2021 se espera una población de 3,078,836 de personas. Con esto calculamos la tasa de homicidios.

Para la primera planilla tenemos una portada simple que destaca los colores del departamento de tránsito de la CABA. Para la segunda planilla tenemos ahora sí el análisis de nuestro KPI, en donde cabe resaltar que nos centramos en un análisis simple en el dashboard, son datos sensibles que estamos utilizando, por lo tal la simpleza para destacar su importancia es la base de nuestro análisis.

En esta segunda plantilla contamos con una matriz para filtrar por años, luego una selección de semestre, una pequeña lista con las victimas de ese año y semestre por tipo de transportación. En el centro nos encontramos una gráfica de barras, la cual nos indica el tipo de incidente que se tuvo (los involucrados) y cuantas victimas por incidente ocurrieron. A los costados tenemos en la parte superior nuestra tasa de homicidio, debajo el recuento de victimas para ese año y semestre, para terminar en la parte inferior tenemos el top offender que generó más victimas ese año. 

En la tercera plantilla nos encontramos con el KPI de los accidentes fatales en moto, por lo cual nos enfocamos en la cantidad de victimas de tipo *”moto”* que se suscitaron en cada año.  En esta plantilla tenemos en la esquina superior izquierda un menú desplegable en el cual podemos observar los datos del tipo de víctima, que para este análisis el que más nos importa es el de moto. Después tenemos un slide de los años en los que queremos analizar este recuento de víctimas, debajo de estos dos contamos con una gráfica que nos muestra los top 4 de acusados que generaron victimas mortales de nuestro tipo de victima seleccionado. En la esquina superior derecha tenemos nuestro KPI, el indicador de victimas del año sobre nuestra victima seleccionada. Debajo de este tenemos el top offender de acusado que generó más víctimas mortales del tipo de victima seleccionado. 

Y para la cuarta planilla tenemos nuestro KPI propuesto el cual es:

- Disminuir un 10% la cantidad de victimas mortales en horas pico dentro de la CABA.

Para esto tenemos una gráfica, la cual podemos monitorear por periodos de años o un año en específico. La cual nos indica el top de victimas mortales por hora en la CABA dentro del periodo o año seleccionado. Con esto podemos visualizar nuestro top de victimas por hora y en que hora sucedió, para así tener un monitoreo de nuestra hora pico y tomar cartas en el asunto. En la esquina inferior izquierda tenemos una lista que nos indica por hora cuantas victimas y de que tipo de victima tenemos.
