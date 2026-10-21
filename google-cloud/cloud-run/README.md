# Cloud Run

**Cloud Run** es la plataforma **serverless de contenedores** de Google Cloud. Tú entregas código o un contenedor, y Google lo ejecuta, lo escala (incluso a cero) y te cobra solo por lo que usas. No hay servidores ni clusters que administrar.

En los últimos años dejó de ser "solo un sitio donde correr un contenedor" y absorbió a Cloud Functions. Ahora es **un paraguas con varios tipos de recursos**:

## Los tipos de recurso

| Recurso | Qué es | Se activa con | Ejemplo |
|---|---|---|---|
| **Services** | Un contenedor que atiende peticiones HTTP/gRPC/WebSocket con una URL | Peticiones | API REST, web app, backend móvil |
| **Functions** | Una función de código; Google crea el contenedor por ti | HTTP o eventos (Eventarc) | "Cuando se suba un archivo, procésalo" |
| **Jobs** | Un contenedor que corre una tarea **hasta terminar**, sin URL | Manual, Scheduler o workflows | ETL nocturno, migraciones, procesamiento por lotes |
| **Worker pools** | Contenedores que corren continuamente sin recibir HTTP | Siempre encendidos | Consumidores de colas (Pub/Sub, Kafka) |

Worker pools es lo más reciente. Revisa en la documentación si ya está disponible de forma general en tu región.

## Qué lo caracteriza

- **Escala a cero:** sin tráfico no hay instancias ni costo de cómputo. Con tráfico escala hasta miles de instancias.
- **Cualquier lenguaje:** si corre en un contenedor Linux, corre en Cloud Run. Con `--source` ni siquiera necesitas un `Dockerfile`, porque usa buildpacks.
- **Pago por uso:** CPU y memoria por segundo, más las peticiones.
- **GPUs:** se pueden adjuntar GPUs (NVIDIA L4 y otras) para **inferencia de IA**, por ejemplo servir modelos open source.
- **Revisiones y tráfico:** cada despliegue crea una revisión inmutable y puedes repartir tráfico entre ellas (canary, rollback inmediato).
- **Integraciones:** Cloud SQL, VPC, Secret Manager, Eventarc, Pub/Sub, IAM, dominios personalizados, balanceadores, etc.

## Estructura
```
Cloud Run
├── Services   
├── Functions  
├── Jobs       
└── Worker pools
```

Las imágenes de todos ellos se guardan en **Artifact Registry** (el reemplazo de `gcr.io`), y los health checks. aplican sobre todo a los **services**.

## Cuándo no es la mejor opción

- Necesitas control total del sistema operativo o procesos muy especiales → **Compute Engine** (VMs).
- Tienes muchos microservicios con orquestación compleja, *sidecars* avanzados o necesitas Kubernetes → **GKE**.
- Un sitio puramente estático → **Firebase Hosting** o **Cloud Storage + CDN**.
