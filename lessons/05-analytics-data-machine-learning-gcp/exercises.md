# Lección 5 — Ejercicios

## Ejercicio 1: Ejecutar una consulta en BigQuery desde Python

1. Configura tus credenciales de GCP para que tus scripts de Python puedan autenticarse correctamente.
2. Instala la biblioteca `google-cloud-bigquery` si aún no lo has hecho.
3. Escribe un script de Python que ejecute una consulta que devuelva todos los registros de una tabla de BigQuery donde un campo específico cumpla una cierta condición.
4. Ejecuta el script y verifica que los resultados sean correctos.
5. Refactoriza el script para manejar posibles errores en la ejecución de la consulta.

## Ejercicio 2: Crear un pipeline de datos simple usando Dataflow

1. Instala el SDK de Apache Beam para Python.
2. Define un pipeline que lea datos de un archivo en Cloud Storage.
3. Transforma los datos aplicando una función personalizada que modifique el contenido de cada registro.
4. Escribe los resultados transformados a una tabla de BigQuery.
5. Ejecuta el pipeline en Dataflow y verifica que los datos se procesen correctamente.

## Ejercicio 3: Explorar Vertex AI con un ejemplo de AutoML

1. Accede a la consola de Vertex AI en Google Cloud Platform.
2. Crea un nuevo dataset utilizando datos de ejemplo proporcionados por Vertex AI.
3. Define un experimento de AutoML para entrenar un modelo con tu dataset.
4. Despliega el modelo entrenado en un endpoint para realizar inferencias.
5. Prueba el endpoint con datos de prueba y analiza los resultados obtenidos.

## Ejercicio 4: Optimizar una consulta SQL con la ayuda de IA

1. Escribe una consulta SQL en BigQuery que realice un cálculo complejo sobre una tabla grande.
2. Utiliza herramientas de IA para analizar la consulta y recibir recomendaciones de optimización.
3. Refactoriza la consulta siguiendo las sugerencias recibidas.
4. Ejecuta ambas versiones de la consulta (original y optimizada) y compara el tiempo de ejecución.
5. Documenta las diferencias en el rendimiento y las modificaciones realizadas.

## Ejercicio 5: Implementar sugerencias de IA para mejorar un pipeline de Dataflow

1. Crea un pipeline de Dataflow que procese un flujo continuo de datos desde Pub/Sub.
2. Revisa el pipeline con herramientas de IA y recibe sugerencias de optimización.
3. Implementa las sugerencias y ajusta el pipeline para mejorar su rendimiento.
4. Monitorea el pipeline para verificar que las optimizaciones han sido efectivas.
5. Presenta un informe detallando las mejoras logradas y el impacto en el rendimiento.
