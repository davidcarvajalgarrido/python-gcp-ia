# Lección 4 — Soluciones

## Ejercicio 1: Conectar una aplicación Python con Google Cloud Storage

Para conectar una aplicación Python con Google Cloud Storage, primero debes autenticarte usando las credenciales de la cuenta de servicio:

```python
from google.cloud import storage

client = storage.Client.from_service_account_json('ruta/a/credenciales.json')
buckets = list(client.list_buckets())
print(buckets)
```

Este script listará todos los buckets en tu proyecto, verificando que la conexión es exitosa.

## Ejercicio 2: Crear una función en Google Cloud Functions

Al crear tu función en Google Cloud Functions, asegúrate de seleccionar 'HTTP Trigger' como el tipo de activador. Aquí tienes un ejemplo básico de función:

```python
def hello_world(request):
    return '¡Hola, mundo!'
```

Despliega la función y verifica su funcionamiento accediendo a la URL proporcionada por Google Cloud.

## Ejercicio 3: Configurar un flujo de trabajo con Pub/Sub

Primero, crea un tópico en Pub/Sub. Luego, utiliza el siguiente script para publicar mensajes:

```python
from google.cloud import pubsub_v1

publisher = pubsub_v1.PublisherClient()
topic_path = publisher.topic_path('tu-proyecto', 'tu-topico')
publisher.publish(topic_path, b'Hola desde Pub/Sub!')
```

Asegúrate de tener una función de Cloud Functions desplegada que procese estos mensajes y los registre.

## Ejercicio 4: Analizar logs de Cloud Functions usando AI

Utiliza Cloud Logging para acceder a los registros de tus funciones. Puedes configurar filtros para identificar patrones de error. Luego, aplica herramientas de IA para analizar estos patrones y recibir sugerencias sobre cómo mejorar el rendimiento de tus funciones.

## Ejercicio 5: Diseñar un microservicio serverless en GCP

Diseña un flujo que integre varios servicios. Por ejemplo, una función puede procesar datos de Pub/Sub y guardar resultados en Cloud Storage. Asegúrate de que cada servicio esté correctamente configurado y que las credenciales de acceso estén en su lugar para permitir la comunicación entre los componentes.
