# 05. Análisis, datos y machine learning básico en GCP

- [Introducción](#introducción)
- [Uso de BigQuery desde Python para análisis avanzado](#uso-de-bigquery-desde-python-para-análisis-avanzado)
- [Integración con Dataflow y almacenamiento de datos masivos](#integración-con-dataflow-y-almacenamiento-de-datos-masivos)
- [Introducción a Vertex AI: visión general para desarrolladores](#introducción-a-vertex-ai-visión-general-para-desarrolladores)
- [IA integrada: generación de consultas, explicación de outputs y optimización de pipelines](#ia-integrada-generación-de-consultas-explicación-de-outputs-y-optimización-de-pipelines)
- [Recursos adicionales](#recursos-adicionales)

## Introducción
En esta lección, exploraremos cómo utilizar herramientas de Google Cloud Platform (GCP) para realizar análisis de datos avanzados y un acercamiento básico al machine learning. Aprenderemos a integrar BigQuery y Dataflow con Python, y veremos una introducción a Vertex AI para desarrolladores.

## Uso de BigQuery desde Python para análisis avanzado
BigQuery es una herramienta poderosa para el análisis de grandes volúmenes de datos. Desde Python, puedes interactuar con BigQuery utilizando la biblioteca `google-cloud-bigquery`. Esta biblioteca permite ejecutar consultas SQL directamente desde tus scripts de Python.

Para comenzar, necesitas instalar la biblioteca utilizando pip:

```bash
pip install google-cloud-bigquery
```

Una vez instalada, puedes autenticarte y ejecutar consultas. Asegúrate de configurar correctamente tus credenciales de GCP. Aquí tienes un ejemplo básico para ejecutar una consulta:

```python
from google.cloud import bigquery

client = bigquery.Client()
query = """
SELECT name, count FROM `myproject.mydataset.mytable`
WHERE count > 1000
"""
query_job = client.query(query)

for row in query_job:
    print(f"Nombre: {row.name}, Conteo: {row.count}")
```

Este código conecta a BigQuery, ejecuta una consulta y muestra los resultados. Es importante manejar adecuadamente los resultados y errores para aplicaciones más complejas.
## Integración con Dataflow y almacenamiento de datos masivos
Dataflow es una herramienta de GCP para procesar datos en tiempo real y por lotes. Puedes usar Dataflow con el SDK de Apache Beam para Python. Esto te permite crear pipelines de procesamiento de datos de manera eficiente.

Primero, necesitas instalar el SDK de Beam:

```bash
pip install apache-beam[gcp]
```

Un pipeline básico en Dataflow puede definirse de la siguiente manera:

```python
import apache_beam as beam

def run_pipeline():
    with beam.Pipeline() as pipeline:
        (pipeline
         | 'Read from PubSub' >> beam.io.ReadFromPubSub(subscription='projects/myproject/subscriptions/mysubscription')
         | 'Transform data' >> beam.Map(lambda message: message.decode('utf-8').upper())
         | 'Write to BigQuery' >> beam.io.WriteToBigQuery('myproject:mydataset.mytable'))

run_pipeline()
```

Este ejemplo lee mensajes de Pub/Sub, los transforma y escribe los resultados en BigQuery. La integración con Dataflow permite escalar el procesamiento de datos sin gestionar la infraestructura subyacente.
## Introducción a Vertex AI: visión general para desarrolladores
Vertex AI es la plataforma de Google Cloud para implementar modelos de machine learning (ML). Proporciona herramientas para entrenar modelos, gestionar datasets y desplegar modelos de manera eficiente.

Vertex AI simplifica el proceso de ML permitiendo a los desarrolladores centrarse más en el desarrollo de modelos y menos en la infraestructura. Puedes crear un modelo utilizando AutoML o llevar tu propio modelo entrenado.

Una visión general del flujo de trabajo en Vertex AI incluye:

1. **Preparación de datos**: Usa BigQuery o Cloud Storage para almacenar tus datos.
2. **Entrenamiento**: Define un experimento de entrenamiento en Vertex AI.
3. **Despliegue**: Despliega el modelo en un endpoint para inferencia.

La plataforma también ofrece herramientas para monitorizar el rendimiento y ajustar los modelos según sea necesario.
## IA integrada: generación de consultas, explicación de outputs y optimización de pipelines
La integración de herramientas de inteligencia artificial (IA) en tus flujos de trabajo en GCP puede mejorar significativamente la eficiencia y la productividad. Las herramientas de IA pueden ayudarte a generar consultas SQL optimizadas, explicar resultados complejos y sugerir mejoras en los pipelines de datos.

Por ejemplo, al usar asistentes de IA, puedes obtener recomendaciones sobre cómo estructurar tus consultas para mejorar el rendimiento o detectar cuellos de botella en tus pipelines de Dataflow.

Implementar estas tecnologías no solo ahorra tiempo, sino que también permite a los desarrolladores centrarse en tareas más estratégicas y creativas, aprovechando al máximo las capacidades de GCP.


## Recursos adicionales
> **Enlaces externos**: Los enlaces se abren en la misma pestaña. Usa Ctrl+Click (Windows/Linux) o Cmd+Click (Mac) para abrirlos en pestaña nueva.

- <a href="https://cloud.google.com/bigquery/docs" target="_blank">Google Cloud BigQuery Documentation</a>
- <a href="https://cloud.google.com/dataflow/docs" target="_blank">Google Cloud Dataflow Documentation</a>
- <a href="https://cloud.google.com/vertex-ai/docs/general" target="_blank">Vertex AI Overview</a>
