# Lección 2 — Soluciones

## Ejercicio 1: Solución al Ejercicio 1

Para crear una máquina virtual en Compute Engine, accedemos a la consola de GCP, navegamos a la sección de Compute Engine, y seguimos el asistente para configurar y lanzar una nueva instancia. Utilizamos la opción de conexión SSH para verificar su estado.

## Ejercicio 2: Solución al Ejercicio 2

En la consola de GCP, vamos a Cloud Storage, creamos un nuevo bucket seleccionando 'nearline' como clase de almacenamiento, subimos un archivo de prueba, y confirmamos su accesibilidad desde el navegador.

## Ejercicio 3: Solución al Ejercicio 3

Creamos una base de datos MySQL en Cloud SQL, configuramos las credenciales de acceso y escribimos un script Python usando `mysql-connector-python` para conectarnos y ejecutar una consulta simple:

```python
import mysql.connector

conn = mysql.connector.connect(
    host='your-cloud-sql-instance-ip',
    user='your-username',
    password='your-password',
    database='your-database'
)

cursor = conn.cursor()
cursor.execute("SELECT * FROM your_table")
for row in cursor.fetchall():
    print(row)

conn.close()
```

## Ejercicio 4: Solución al Ejercicio 4

Creamos una imagen Docker de nuestra aplicación, la subimos a Google Container Registry, y desde allí, la desplegamos en Cloud Run usando la consola de GCP. Verificamos que el servicio esté accesible a través de la URL proporcionada por Cloud Run.

## Ejercicio 5: Solución al Ejercicio 5

En Firestore, creamos una nueva colección. Utilizamos el siguiente script Python para almacenar y recuperar datos:

```python
from google.cloud import firestore

db = firestore.Client()

# Almacenar datos
doc_ref = db.collection('your-collection').document('your-document')
doc_ref.set({
    'field1': 'value1',
    'field2': 'value2',
})

# Recuperar datos
doc = doc_ref.get()
print(f'Document data: {doc.to_dict()}')
```
