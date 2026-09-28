# telecom-analysis ConnectaTel — Análisis de Clientes y Uso
Descripción del proyecto
Este proyecto realiza un análisis exploratorio y de segmentación de clientes para ConnectaTel, utilizando información de usuarios y de su comportamiento de uso durante 2024.
El objetivo principal es transformar los datos disponibles en información útil para el negocio, identificando patrones de uso, problemas de calidad de datos, valores atípicos y segmentos de clientes que puedan servir como base para mejorar la oferta comercial y la toma de decisiones.

Objetivos
Revisar y limpiar la calidad de los datos.
Identificar valores nulos, valores sentinel y fechas imposibles.
Analizar el comportamiento de uso de los clientes.
Construir métricas agregadas por usuario.
Comparar la distribución de clientes según su plan.
Detectar valores atípicos mediante el método IQR.
Segmentar a los clientes por edad y nivel de uso.
Generar insights y recomendaciones accionables para stakeholders.

Datasets utilizados
`users`
Contiene información general de los clientes, como:
`user\_id`
`age`
`city`
`plan`
`reg\_date`
`churn\_date`
`usage`
Contiene información histórica del uso de los servicios, incluyendo:
`user\_id`
`type`
`date`
`duration`
`length`
A partir de `usage` se construyen métricas agregadas por cliente:
`cant\_mensajes`
`cant\_llamadas`
`cant\_minutos\_llamada`

Etapas del análisis
1. Exploración inicial
Se revisaron dimensiones, tipos de datos, valores nulos, duplicados, valores inconsistentes y fechas fuera del rango esperado.
2. Limpieza de datos
Se corrigieron o evaluaron valores sentinel como `-999` y `"?"`, fechas imposibles, valores nulos y nulos estructurales en `duration` y `length`.
3. Construcción de métricas por usuario
Se agregó la información de `usage` por `user\_id` para obtener cantidad total de mensajes, cantidad total de llamadas y minutos totales de llamada. Después se combinaron estas métricas con `users`.
4. Resumen estadístico
Se analizaron media, mediana, mínimo, máximo, desviación estándar y distribución porcentual del tipo de plan.
5. Visualización y detección de outliers
Se construyeron histogramas para `age`, `cant\_mensajes`, `cant\_llamadas` y `cant\_minutos\_llamada`, además de boxplots y análisis mediante IQR.
6. Segmentación de clientes
Segmentación por uso
Bajo uso: llamadas < 5 y mensajes < 5
Uso medio: llamadas < 10 y mensajes < 10
Alto uso: resto de los casos
Segmentación por edad
Joven: edad < 30
Adulto: 30 ≤ edad < 60
Adulto Mayor: edad ≥ 60
7. Insight ejecutivo
Los hallazgos se tradujeron en conclusiones orientadas al negocio, considerando calidad de datos, distribución de clientes, comportamiento de uso, clientes intensivos, oportunidades de upselling y diferenciación de planes.


Cómo ejecutar el proyecto
Opción 1: Google Colab
Descarga o clona este repositorio.
Abre el archivo `.ipynb`.
Súbelo a Google Colab.
Carga los archivos de datos requeridos.
Ejecuta las celdas en orden desde el inicio.
Opción 2: Jupyter Notebook
```bash
git clone <URL\_DEL\_REPOSITORIO>
cd <NOMBRE\_DEL\_REPOSITORIO>
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook
```
Después abre el notebook principal y ejecuta las celdas en orden.
