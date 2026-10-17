# connectatel-analysis
Customer segmentation and usage analysis using Python, Pandas and Seaborn.


ConnectaTel — Análisis y Segmentación de Clientes

📌 Descripción del proyecto

Este proyecto tiene como objetivo analizar las características demográficas y los patrones de uso de los clientes de ConnectaTel, una empresa de telecomunicaciones. A partir de los datos disponibles, se busca identificar segmentos de clientes y generar conclusiones que permitan detectar oportunidades de mejora en la oferta de planes y servicios.

🎯 Objetivos

Explorar las características demográficas de los clientes.

Identificar valores faltantes y posibles valores atípicos (outliers).

Analizar los patrones de uso de llamadas y mensajes.

Segmentar a los clientes según su edad y nivel de uso.

Visualizar la distribución de los segmentos identificados.

Elaborar recomendaciones comerciales basadas en los resultados.

🛠️ Herramientas utilizadas

Python: lenguaje de programación utilizado para el análisis.

Pandas: manipulación y análisis de datos.

NumPy: operaciones y tratamiento de datos.

Matplotlib: creación de gráficos.

Seaborn: visualización de datos estadísticos.

Google Colab: entorno de desarrollo del notebook.

GitHub: almacenamiento y documentación del proyecto.

🔎 Etapas del análisis

Exploración inicial de los datos y revisión de las variables.

Evaluación de la calidad de los datos, incluyendo valores faltantes y valores atípicos.

Análisis de las variables demográficas y métricas de uso.

Segmentación de clientes por nivel de uso.

Segmentación de clientes por edad.

Visualización de la distribución de los segmentos.

Elaboración de un análisis ejecutivo con conclusiones y recomendaciones para el negocio.

👥 Segmentación de clientes

Por nivel de uso:

Bajo uso: menos de 5 llamadas y menos de 5 mensajes.

Uso medio: no cumple la condición de bajo uso, pero tiene menos de 10 llamadas y menos de 10 mensajes.

Alto uso: no cumple ninguna de las condiciones anteriores.

Por edad:

Joven: menor de 30 años.

Adulto: entre 30 y 59 años.

Adulto mayor: 60 años o más.

Los clientes sin información suficiente en las variables necesarias se mantienen sin clasificar.

📊 Principales resultados

Entre los clientes con información suficiente para la segmentación se obtuvieron los siguientes resultados:

Por nivel de uso:

Uso medio: 2.917 clientes.

Bajo uso: 766 clientes.

Alto uso: 276 clientes.

Por edad:

Adultos: 2.000 clientes.

Adultos mayores: 1.209 clientes.

Jóvenes: 751 clientes.

El segmento de uso medio es el más numeroso, mientras que los adultos representan el grupo de edad con mayor cantidad de clientes. Estos hallazgos permiten plantear hipótesis sobre la adecuación de los planes actuales y las posibles necesidades de los distintos perfiles.

💡 Recomendaciones comerciales

Evaluar planes flexibles para clientes de bajo uso.

Analizar alternativas con mayor capacidad para clientes de alto uso.

Cruzar los segmentos por edad y nivel de uso para identificar perfiles más específicos.

Investigar los valores atípicos antes de decidir si requieren un tratamiento especial.

Complementar el análisis con información de ingresos, rentabilidad y cancelaciones para validar las oportunidades comerciales.

▶️ Cómo reproducir el análisis

1 Clonar o descargar este repositorio.

2 Abrir el notebook .ipynb en Google Colab o Jupyter Notebook.

3 Cargar los archivos CSV disponibles en la carpeta data/.

4 Verificar que las rutas de lectura de los archivos coincidan con la ubicación de los datasets.

5 Ejecutar las celdas en orden para reproducir el análisis, las visualizaciones y las conclusiones.

Los archivos de datos necesarios para el análisis se incluyen en este repositorio para facilitar su reproducción.

⚠️ Limitaciones

La segmentación permite identificar patrones de uso, pero no determina por sí sola la rentabilidad ni el riesgo de cancelación de cada grupo. Para validar las recomendaciones comerciales será necesario incorporar información adicional sobre ingresos, costos y abandono de clientes.

👩‍💻 Autora

Proyecto desarrollado como parte de mi formación en análisis de datos, aplicando técnicas de exploración, limpieza, segmentación y visualización con Python.
