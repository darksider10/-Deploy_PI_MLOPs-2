# PI_MLOPs-2


#Análisis de Siniestros Viales en Buenos Aires

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

#Desarrollo:

Este proyecto se basa en la exploración y análisis de datos relacionados con siniestros viales en la ciudad de Buenos Aires. Se utiliza un conjunto de datos que incluye dos pestañas principales:

    HECHOS:
        Contiene información detallada sobre cada incidente, con un identificador único (id) y variables temporales, espaciales y de participantes asociadas.

    VICTIMAS:
        Proporciona detalles sobre cada víctima involucrada en los incidentes, incluyendo edad, sexo y modo de desplazamiento. Se vincula a los datos de HECHOS mediante el id del incidente.

ETL

El primer paso del proyecto involucra la extracción y limpieza de datos de los conjuntos HECHOS y VICTIMAS. Este proceso se realiza utilizando herramientas como Pandas y Jupyter Notebook. Se eliminan valores nulos, duplicados, y se aplican transformaciones necesarias, como cambios en los tipos de datos, eliminación de columnas irrelevantes y unión de las tablas. El resultado se guarda en un archivo siniestros_viales.csv.

 #Eliminación de la columna "Altura" del DataFrame homicidios_hechos debido a la cantidad de nulos que posee.
 
 #Filtrado de posiciones no válidas en las columnas 'pos x' y 'pos y'.
 
 #Conversión de las columnas 'pos x' y 'pos y' a tipo numérico (float).
 
 #Manipulación de la columna 'XY (CABA)' para obtener 'X_CABA' y 'Y_CABA'.
 
 #Creación de nuevas columnas como 'Dia semana' basada en la columna 'Fecha'.
 
 #Fusión de DataFrames (comunas y homicidios_hechos) y crear una columna de comunas para el analisi geografico posterior.
 
 #Manipulación de fechas, conversión de edades a formato numérico y creación de la columna 'Rango_etario'.

EDA

Con los datos limpios, se procede a realizar un Análisis Exploratorio de Datos (EDA). Durante esta fase, se exploran las relaciones entre variables numéricas y categóricas, se identifican posibles outliers o anomalías, y se busca patrones que puedan proporcionar conocimientos para análisis posteriores.

Se examinaron las variables numéricas del conjunto de datos mediante una matriz de correlación, destacando una relación positiva entre las variables Edad y Hora.

La mayoría de los siniestros concluyen con una única víctima fatal; casos que involucran a tres víctimas son poco frecuentes.

#En el transcurso de los años, los accidentes con víctimas fatales muestran: para el período 2016-2018 una tendencia alta y estacionaria, que luego se convierte en bajista (teniendo en cuenta el comienzo de la Pandemia por COVID19 durante 2020)

Puede verse un pico de siniestros durante Diciembre de 2021 y se retoma la tendencia bajista.

Los meses con más victimas fatales son **Diciembre** (86), mientras que los días de la semana **Sábado** (115) y **Domingo** (117) tienen la mayor cantidad de víctimas.

![Mapa de Color](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/dia%20y%20horas.png)

Los horarios críticos de los siniestros viales están relacionados con los momentos del ingreso a la jornada laboral (5-9h), el momento del almuerzo (12-14h) y la salida del trabajo (17-18h). Mientras que los fines de semana están relacionados con las salidas nocturnas (4-7h).

![linea](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/victimas_tiempo.png)

El mayor número de víctimas en promedio se registró entre 2017 y 2019. En 2020, hubo un marcado descenso en el número de muertes, lo cual asumo que puede estar relacionado con el inicio de la pandemia de COVID-19. A finales de 2020, se observó un pico significativamente alto de víctimas, lo cual podría indicar eventos específicos o cambios en las condiciones de tráfico.

![Torta](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/distribucion_sexos.png)

![Roles](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/roles.png)

La distribución por roles de las víctimas revela que:

#En la mayoría de los siniestros, las víctimas desempeñan el rol de conductor, seguido por el rol de peatón.

#Para las víctimas de sexo masculino, el rol más común en los siniestros es el de conductor, seguido por el rol de peatón.

#En el caso de las víctimas de sexo femenino, el rol más frecuente en los siniestros es el de peatón, seguido por el rol de pasajero-acompañante.

Estos patrones proporcionan una perspectiva detallada sobre la distribución de roles en los incidentes viales, tanto en general como diferenciando por género.

![Roles](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/vehiculos_sexos.png)

#La mayor cantidad de accidentes con víctimas fatales involucran a motociclistas, siendo este el grupo con mayor proporción de víctimas masculinas. En segundo lugar, se encuentran los peatones, donde también la mayoría de las víctimas son masculinas, aunque la diferencia en proporción es menor en comparación con el primer grupo.

Edad de las víctimas : La distribución del rango etario de víctimas, resulta para los `Masculinos` entre 20 y 40 años; mientras que para los `Femeninos` entre 40, 60 y 80 años.


![Edades](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/victimas_sexo%20y%20edad.png)

Se puede visualizar que el mayor número de víctimas son Moto, Peaton y Auto.

![vehiculos](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/victimas_distribucion.png)

La gráfica muestra la concentración de los puntos rojos representando siniestros con víctimas fatales, hacia la zona Este del mapa de CABA sobre la comuna 1 y 4.

![Mapa](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/victimas_gp.png)


Del análisis del gráfico resulta que el mayor número de víctimas fatales se producen en Avenida, seguido por Calle y ademas cuadra con la conclusion anterior. Esto se debe tanto al horario de entrada y salida laboral, como al trafico en las arterias entre comunas. 

![Proporcion](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/victimas_calles.png)


#KPIs

Los KPIs propuestos son: 


Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior.

Definimos a la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000

Termino dando un 14% mayor al esperado.
![KPI](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/KPI1.png)

Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior.

Definimos a la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100

Termino dando un 46% negativo al esperado.

![KPI](https://raw.githubusercontent.com/darksider10/PI_MLOPs-2/main/imagenes/KPI2.png)

#Conclusion:
Luego de realizar un análisis exhaustivo de los datos y presentarlos visualmente a través del dashboard en PowerBi, se obtienen las siguientes conclusiones:

    Entre los años 2016 y 2021, se registraron 717 víctimas fatales en siniestros de tránsito.
    La franja horaria con mayor incidencia de siniestros se encuentra durante las horas de ingreso laboral (5-9h), almuerzo (12-14h), y regreso a casa (17-18h). Los fines de semana, especialmente los Sábados y Domingos, los accidentes se manifiestan en horarios de salidas nocturnas (3-7h).
    El 76% de las víctimas son de género masculino, y la mayoría se encuentra en el rango etario de 20-40 años.
    En siniestros que involucran a hombres, el rol más común es el de conductor.
    Los tipos de vehículos más frecuentes con víctimas son las motocicletas, seguidas por peatones. En cuanto a los acusados, los vehículos más comunes son autos, colectivos y vehículos de carga.
    Las avenidas son los lugares con mayor cantidad de siniestros a lo largo de los años, y los cruces representan la mayoría de las ubicaciones.
    Se observa un patrón relacionado con la edad, hora y género. Los hombres de 20 a 40 años tienen una mayor incidencia de accidentes, especialmente durante las horas de entrada y salida laboral, así como en las salidas nocturnas de los fines de semana.

fuentes de informacion adicional:https://www.minfra.gba.gob.ar/web/seguridadVial/Informe%202019%20Estadisticas%20en%20Seguridad%20Vial.pdf

INDEC
