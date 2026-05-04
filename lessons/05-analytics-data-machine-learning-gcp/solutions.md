# Lección 5 — Soluciones

## Ejercicio 1: Ejecutar una consulta en BigQuery desde Python

Para ejecutar una consulta en BigQuery desde Python, primero asegúrate de que tus credenciales de GCP están configuradas. Luego, instala la biblioteca `google-cloud-bigquery`. Aquí tienes un ejemplo de script que puede servirte de referencia:

```python
from google.cloud import bigquery

client = bigquery.Client()
query = """
SELECT * FROM `myproject.mydataset.mytable`
WHERE myfield > 100
"""
query_job = client.query(query)

for row in query_job:
    print(row)
```

Asegúrate de manejar excepciones potenciales usando bloques try-except.

## Ejercicio 2: Crear un pipeline de datos simple usando Dataflow

Para crear un pipeline de datos en Dataflow, instala el SDK de Apache Beam y define tu pipeline. Aquí tienes un ejemplo básico:

```python
import apache_beam as beam

def transform(record):
    return record.lower()

with beam.Pipeline() as pipeline:
    (pipeline
     | 'Read from GCS' >> beam.io.ReadFromText('gs://mybucket/myfile.txt')
     | 'Transform text' >> beam.Map(transform)
     | 'Write to BigQuery' >> beam.io.WriteToBigQuery('myproject:mydataset.mytable'))
```

Este pipeline transforma el texto a minúsculas y lo escribe en BigQuery.

## Ejercicio 3: Explorar Vertex AI con un ejemplo de AutoML

En Vertex AI, puedes usar AutoML para crear modelos de ML fácilmente. Sigue estos pasos básicos:

1. Accede a Vertex AI en la consola de GCP.
2. Crea un dataset importando datos de Cloud Storage o BigQuery.
3. Configura un experimento de AutoML para entrenar un modelo.
4. Despliega el modelo en un endpoint y realiza inferencias con datos de prueba.

La consola de Vertex AI te guiará a través de cada paso con interfaces intuitivas.

## Ejercicio 4: Optimizar una consulta SQL con la ayuda de IA

Para optimizar una consulta SQL en BigQuery, primero escribe una consulta compleja. Luego, utiliza herramientas de IA para obtener sugerencias. Por ejemplo, puedes recibir recomendaciones para usar índices o reestructurar subconsultas. Comparar los tiempos de ejecución te mostrará claramente las mejoras logradas.

## Ejercicio 5: Implementar sugerencias de IA para mejorar un pipeline de Dataflow

Al utilizar IA para optimizar un pipeline de Dataflow, puedes identificar cuellos de botella y aplicar mejoras sugeridas. Esto podría incluir la paralelización de ciertas etapas o el ajuste de parámetros de configuración. Monitorizar el rendimiento tras las optimizaciones confirmará su efectividad y te permitirá documentar el impacto positivo en el procesamiento de datos.
