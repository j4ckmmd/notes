Multiregion: El servicio va a tener redundancia en varias regiones
Region: Son ubicaciones físicas orientada a continentes.
Zone: Están dentro de las regiones, son los datacentes más específicas.
- europe-west2-a
- europe-west2-b
- europe-west2-c

Las letras al final es la zona que se encuentra más actualizada.

## Compute

- Compute Engine: Máquinas virtuales configurables.
- Kubernetes Engine: Ejecuta y administra contenedores con Kubernetes.
- App Engine: Despliega aplicaciones sin administrar servidores.
- Cloud Functions: Ejecuta funciones en respuesta a eventos.

## Storage

- Bigtable: Base de datos NoSQL para grandes volúmenes de datos.
- Cloud Storage: Almacena archivos, imágenes, videos y documentos.
- Cloud SQL: Bases de datos SQL administradas.
- Cloud Spanner: Base de datos SQL distribuida y escalable.
- Cloud Datastore: Base de datos NoSQL orientada a documentos.

## Big Data

- BigQuery: Analiza grandes cantidades de datos mediante SQL.
- Pub/Sub: Envía eventos y mensajes entre servicios.
- Dataflow: Procesa y transforma datos.
- Dataproc: Ejecuta Spark y Hadoop para procesar datos.
- Datalab: Entorno de notebooks para análisis de datos.

## Machine Learning

- Natural Language API: Analiza y comprende texto.
- Vision API: Analiza imágenes y detecta objetos o texto.
- Vertex AI: Desarrolla, entrena y despliega modelos de IA/ML.

## Cloud Shell

Cloud Sheel es gratis y ya tiene instalado gcloud

Obtener ayuda con respecto a compute engine
```sh
gcloud compute --help
```
Lista las instancias de maquinas virtuales
```sh
gcloud compute instances list
```

## Políticas

- Google acount or Cloud Identity user: (test@gmail.com) or (test@example.com)
- Service account: Cuenta en la nube para servicios de Google Cloud (test@project_id.iam.gserviceaccount.com)
- Google group: test@googlegroups.com
- Cloud Identity or G Suite domain: example.com

Objetos de cloud IAM
- Organizaciones
- Folders
- Proyectos
- Roles
- Miembros
- Recursos
- Productos

