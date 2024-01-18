# -Deploy_PI_MLOPs-2

Fuente de datos adicional:https://www.minfra.gba.gob.ar/web/seguridadVial/Informe%202019%20Estadisticas%20en%20Seguridad%20Vial.pdf



Análisis de Siniestros Viales en Buenos Aires

Los siniestros viales, comúnmente conocidos como accidentes de tráfico, representan eventos que involucran vehículos en las vías públicas, con consecuencias que pueden variar desde daños materiales hasta lesiones graves o fatales. En el contexto de una ciudad como Buenos Aires, la alta densidad poblacional y el volumen de tráfico hacen que los siniestros viales sean una preocupación importante.
Importancia del Análisis

En la ciudad, la seguridad vial se convierte en una prioridad debido a su impacto en la vida de los residentes, visitantes y en la infraestructura vial. Las tasas de mortalidad relacionadas con siniestros viales son indicadores críticos, calculados por el número de muertes en proporción a la población o vehículos registrados. Reducir estas tasas es fundamental para mejorar la seguridad vial y proteger vidas.
Estrategias de Prevención

La prevención de siniestros viales requiere enfoques integrales, como educación vial, cumplimiento de normas de tráfico, infraestructura segura y vehículos más seguros. El seguimiento estadístico y la implementación efectiva de políticas son esenciales para abordar este desafío de manera efectiva.
Contexto Nacional

En Argentina, los siniestros viales causan alrededor de 4,000 muertes anuales, siendo la principal causa de muertes violentas en el país. Según informes del Sistema Nacional de Información Criminal (SNIC) del Ministerio de Seguridad de la Nación, entre 2018 y 2022 se registraron 19,630 muertes en siniestros viales en todo el país, promediando 11 víctimas fatales por día.

En 2022, se contabilizaron 3,828 muertes fatales. Se destaca que la probabilidad de fallecer en un siniestro vial en Argentina es dos o tres veces mayor que en hechos de inseguridad delictiva, según expertos.
Resumen de Análisis

Este proyecto tiene como objetivo analizar y visualizar datos de siniestros viales en Buenos Aires para comprender mejor los patrones y contribuir a la mejora de la seguridad vial. El análisis se centra en tasas de mortalidad y tendencias a lo largo del tiempo, proporcionando información clave para la toma de decisiones y la implementación de políticas efectivas.

Desarrollo:

Este proyecto se basa en la exploración y análisis de datos relacionados con siniestros viales en la ciudad de Buenos Aires. Se utiliza un conjunto de datos que incluye dos pestañas principales:

    HECHOS:
        Contiene información detallada sobre cada incidente, con un identificador único (id) y variables temporales, espaciales y de participantes asociadas.

    VICTIMAS:
        Proporciona detalles sobre cada víctima involucrada en los incidentes, incluyendo edad, sexo y modo de desplazamiento. Se vincula a los datos de HECHOS mediante el id del incidente.

Puede acceder a los datos utilizados en este análisis aquí.
Proceso de ETL (Extracción, Transformación y Carga)

El primer paso del proyecto involucra la extracción y limpieza de datos de los conjuntos HECHOS y VICTIMAS. Este proceso se realiza utilizando herramientas como Pandas y Jupyter Notebook. Se eliminan valores nulos, duplicados, y se aplican transformaciones necesarias, como cambios en los tipos de datos, eliminación de columnas irrelevantes y unión de las tablas. El resultado se guarda en un archivo siniestros_limpio.csv.
Proceso de EDA (Análisis Exploratorio de Datos)

Con los datos limpios, se procede a realizar un Análisis Exploratorio de Datos (EDA). Durante esta fase, se exploran las relaciones entre variables numéricas y categóricas, se identifican posibles outliers o anomalías, y se busca patrones que puedan proporcionar conocimientos para análisis posteriores.

Analisis

    Se examinaron las variables numéricas del conjunto de datos mediante una matriz de correlación, destacando una relación positiva entre las variables Edad y Hora.
    La mayoría de los siniestros concluyen con una única víctima fatal; casos que involucran a tres víctimas son poco frecuentes.

    En el transcurso de los años, los accidentes con víctimas fatales muestran: para el período 2016-2018 una tendencia alta y estacionaria, que luego se convierte en bajista (teniendo en cuenta el comienzo de la Pandemia por COVID19 durante 2020); puede verse un pico de siniestros durante Diciembre de 2021 y se retoma la tendencia bajista.
Los meses con más victimas fatales son **Diciembre** (86), mientras que los días de la semana **Sábado** (115) y **Domingo** (117) tienen la mayor cantidad de víctimas.

![Mapa de Color](https://raw.githubusercontent.com/darksider10/-Deploy_PI_MLOPs-2/main/imagenes/dia%20y%20horas.png)


Edad de las víctimas : La distribución del rango etario de víctimas, resulta para los `Masculinos` entre 20 y 40 años; mientras que para los `Femeninos` entre 40, 60 y 80 años.


![Edades](https://raw.githubusercontent.com/darksider10/-Deploy_PI_MLOPs-2/main/imagenes/victimas_sexo%20y%20edad.png)




![participantes](https://raw.githubusercontent.com/darksider10/-Deploy_PI_MLOPs-2/main/imagenes/victimas%segun%participantes.png)
