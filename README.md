# DataPT06---POI-02---JaredLuna
*Segundo proyecto individual de Henry, para la carrera de DataScience en PT Cohorte 06.*

Para este proyecto se nos plantea la siguiente problematica:

*"El Observatorio de Movilidad y Seguridad Vial (OMSV), centro de estudios que se encuentra bajo la órbita de la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires, nos solicita la elaboración de un proyecto de anális de datos, con el fin de generar información que le permita a las autoridades locales tomar medidas para disminuir la cantidad de víctimas fatales de los siniestros viales."*

Dentro del mismo se nos plantean las maneras a trabjar. Como en el proyecto pasado primero se tiene que desarrollar la EDA, luego una ETL y finalmente (en este caso) el dashboard. Los datsets que se nos proporcionan estaran en la carpeta de *Datasets*.

Primeramente comenzare a explicar cada una de las partes de dicho desarrollo, del mimos modo todo lo que se fue generando y finalmente los resultados.

## EDA

Para la parte de la EDA primeramente se descargó el dataset con el que se empezó a trabjar. Dicho dataset se encuentra en la carpeta de **Datasets** y se llama "homicidios". En este dataset encontramos varios datos sobre accidentes en la CABA, venían particionados por ID, fechas, calles e involucrados. En ese dataset (que es un archivo CSV), contenia dos horas, la de "hechos" y la de "victimas". Se extrajeron esas dos hojas para poder hacer una relación entre las vicitamas y los involucrados en todos los accidentes, así como para tener un control de las fechas y horas de los accidentes.

Una vez que tuvimos identificadas nuestras hojas objetivo, se procedió a importarlas a dos archivos csv diferentes (uno para cada hoja). Estos archivos igualmente se encuentran en la carpeta de Datasets como:

- HechosEDA

- VictimasEDA

Estos serán los archivos con los que se trabajaron en python para la EDA y la ETL.

Para el comienzo de la EDA primeramente se importaron los archivos CSV con los que ibamos a trabajar para poder visualizarlos. Para más detalle del paso a paso que se realizó en la EDA se puede abrir el archivo de *"EDA.ipynb"* que se encuentra dentro del folder de NoteBooks. En esta inspección nos dimos cuenta de que contabamos con algunas columnas con datos faltantes, al ser varias valores así perderiamos mucha información en su eliminación por lo que se optó por reemplazar los datos faltantes por "SD", pero esto se realizó en la parte de la ETL. 

Una vez que revisamos toda la información, apuntamos los datos pertienentes como comentarios de markdown, se procedió a la transformación de nuestros datos en la parte de la ETL.

# ETL

Para esta parte volvimos a tomar los datos que tenemos en el folder de Datasets para trabajar con ellos. De la misma manera dentro del jupyter notebook se encuentran comentarios más detallados de lo realizado en la transformación de los datos. Fue una transformación sencilla, ya que solamente nos encargamos de reemplazar valores vacios y separar fechas para tener un mejor control de tiempos. Realmente esta parte era opcional en el proyecto pero para tener un dataset más ordenado se realizó esta pequeña limpieza.

Una vez terminada la trasnformación se guardaron los archivos en formato parquet, esto solo para tener unos archivos más livianos y trabajar con ellos en PoweerBi.


# Dashboard en PowerBI

Para esta parte es donde se nos propusieron 2 KPI's más uno extra propuesto por nosotros. Los dos KPI's son:

- Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

- Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

Estos dos KPI's serán generados a partir de varias métricas que se encuentran o se han generado en el proyecto. Como en PowerBi es imposible poner comentarios sobre el proyecto es necesario hacer un poco más detallada esta parte del ReadMe.

### Importación de datos

