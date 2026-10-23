
# ConnectaTel — Análisis y Segmentación de Clientes

Análisis de características demográficas y patrones de uso con Python, pandas y seaborn.

## 📌 Descripción del proyecto

Este proyecto analiza las características demográficas y los patrones de uso de los clientes de ConnectaTel, una empresa de telecomunicaciones con operaciones en México y Colombia.

A partir de tres datasets, se evalúa la calidad de la información, se construyen métricas de actividad por usuario y se identifican segmentos para plantear oportunidades de mejora en la oferta de planes y servicios.

El período de referencia del análisis comprende información registrada hasta 2024.

## 🎯 Objetivos

- Explorar las características demográficas de los clientes.
- Identificar valores faltantes, sentinels y fechas fuera de rango.
- Analizar los patrones de uso de llamadas y mensajes.
- Detectar valores atípicos mediante visualizaciones y el método IQR.
- Segmentar a los clientes según su edad y nivel de uso.
- Visualizar la distribución de los segmentos.
- Elaborar recomendaciones comerciales basadas en los resultados.

## 📂 Datasets utilizados

Los tres archivos CSV se incluyen en la carpeta `data/` del repositorio.

| Archivo | Descripción |
| --- | --- |
| `plans.csv` | Catálogo de planes, precios, beneficios incluidos y costos adicionales. |
| `users_latam.csv` | Información de los clientes: identificador, edad, ciudad, fecha de registro, plan y fecha de cancelación. |
| `usage.csv` | Registros de llamadas y mensajes, incluyendo fecha, duración y longitud del texto. |

En el notebook, los archivos se cargan en los DataFrames `plans`, `users` y `usage`.

## 🛠️ Herramientas utilizadas

- **Python:** lenguaje de programación.
- **pandas:** limpieza, transformación, agregación e integración de datos.
- **NumPy:** operaciones numéricas.
- **Matplotlib:** creación y personalización de gráficos.
- **seaborn:** visualización de distribuciones y segmentos.
- **Jupyter Notebook:** desarrollo y ejecución del análisis.
- **GitHub:** almacenamiento, documentación y control de versiones.

## 🔎 Etapas del análisis

1. Carga y exploración de los tres datasets.
2. Revisión de dimensiones, tipos de datos y valores faltantes.
3. Identificación de sentinels y fechas fuera del período de análisis.
4. Limpieza de edades, ciudades y fechas de registro.
5. Análisis de nulos estructurales según el tipo de actividad.
6. Agregación de mensajes, llamadas y minutos por usuario.
7. Integración de las métricas de uso con la información de clientes.
8. Análisis estadístico y visualización mediante histogramas y boxplots.
9. Detección de outliers con el método del rango intercuartílico (IQR).
10. Segmentación por nivel de uso y edad.
11. Elaboración de conclusiones y recomendaciones comerciales.

## 🧹 Decisiones de limpieza

- Los valores `-999` en `age` se reemplazaron por la mediana de las edades válidas.
- El sentinel `"?"` en `city` se reemplazó por un valor nulo.
- Las 40 fechas de registro posteriores a 2024 se marcaron como nulas únicamente en `reg_date`, conservando las demás columnas de esos usuarios.
- Los nulos estructurales de `duration` y `length` se conservaron: la duración no aplica a los mensajes y la longitud del texto no aplica a las llamadas.
- Los valores atípicos de consumo se mantuvieron porque no había evidencia suficiente para considerarlos errores.
- El usuario sin registros de actividad asociados conservó sus métricas nulas y quedó sin clasificación por nivel de uso.

## 👥 Segmentación de clientes

### Por nivel de uso

- **Bajo uso:** menos de 5 llamadas y menos de 5 mensajes.
- **Uso medio:** no cumple la condición de bajo uso, pero tiene menos de 10 llamadas y menos de 10 mensajes.
- **Alto uso:** 10 o más llamadas, o 10 o más mensajes.

Los usuarios sin información suficiente en estas métricas se mantienen sin clasificar.

### Por edad

- **Joven:** menor de 30 años.
- **Adulto:** de 30 a 59 años.
- **Adulto Mayor:** 60 años o más.

## 📊 Principales resultados

Se conservaron los **4000 usuarios** después de la limpieza. Todos pudieron clasificarse por edad y **3999** por nivel de uso.

### Segmentos por nivel de uso

Los porcentajes se calculan sobre los 3999 usuarios clasificados.

| Segmento | Usuarios | Porcentaje |
| --- | ---: | ---: |
| Uso medio | 2943 | 73.59 % |
| Bajo uso | 778 | 19.45 % |
| Alto uso | 278 | 6.95 % |

La diferencia respecto al 100 % se debe al redondeo.

### Segmentos por edad

Los porcentajes se calculan sobre los 4000 usuarios.

| Segmento | Usuarios | Porcentaje |
| --- | ---: | ---: |
| Adulto | 2018 | 50.45 % |
| Adulto Mayor | 1222 | 30.55 % |
| Joven | 760 | 19.00 % |

### Uso y valores atípicos

- La mediana de actividad fue de **5 mensajes**, **4 llamadas** y **19.78 minutos de llamadas** por usuario.
- Los límites superiores del método IQR fueron **11.50 mensajes**, **10.50 llamadas** y aproximadamente **61.86 minutos**.
- Los máximos observados fueron **17 mensajes**, **15 llamadas** y **155.69 minutos**.
- No se detectaron outliers en la variable de edad según el criterio utilizado.

El segmento de uso medio es el más numeroso, mientras que los adultos representan el grupo de edad con mayor cantidad de clientes. Estos resultados permiten plantear hipótesis comerciales, pero no demuestran qué edades consumen más sin realizar comparaciones adicionales.

## 💡 Recomendaciones comerciales

- Evaluar planes económicos o flexibles para clientes de bajo uso.
- Analizar paquetes de mayor capacidad para usuarios de alto uso.
- Revisar si la oferta actual se ajusta a las necesidades del segmento de uso medio.
- Cruzar los segmentos por edad, nivel de uso y plan contratado para identificar perfiles más específicos.
- Investigar los valores atípicos antes de decidir si requieren corrección o un tratamiento especial.
- Comparar el consumo y los beneficios de los planes sobre un mismo período.
- Complementar el análisis con ingresos, costos y cancelaciones para priorizar las oportunidades comerciales.
- Medir el impacto de futuros cambios mediante indicadores de consumo, ingresos por cliente y tasa de cancelación.

## ▶️ Cómo reproducir el análisis

1. Clonar o descargar el repositorio completo, conservando el notebook y la carpeta `data/` en la carpeta principal.
2. Disponer de Python y las librerías necesarias.
4. Abrir el archivo `.ipynb`.
5. Reiniciar el kernel y ejecutar todas las celdas en orden.

El notebook detecta automáticamente los archivos de la carpeta `data/`.

### Verificación de resultados

Al finalizar la ejecución, comprobar que:

- Se conservan 4000 usuarios.
- `user_id`, `age` y `plan` no presentan valores nulos después de la limpieza.
- Las tres métricas de uso tienen 3999 valores no nulos.
- Los conteos de los segmentos coinciden con los resultados documentados.

## ⚠️ Limitaciones

- La segmentación describe patrones de actividad, pero no determina por sí sola la rentabilidad ni el riesgo de cancelación.
- Las métricas representan el consumo acumulado en los registros analizados y no deben interpretarse como promedios mensuales.
- La ausencia de actividad asociada a un usuario no permite confirmar que su consumo haya sido cero.
- La imputación de edades con la mediana puede influir en la composición de los grupos etarios.
- La falta de ciudad en 565 usuarios limita los análisis geográficos.
- Superar un límite IQR no demuestra un error de registro ni fraude.

## 👩‍💻 Autora

**Malena Spicacci**
