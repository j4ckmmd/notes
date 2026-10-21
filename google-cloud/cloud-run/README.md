## ¿Qué es cloud Run?

Es una plataforma de computación sin servidores (serverless) de google cloud que permite ejecutar código empaquetado en contenedores de forma automática, sin necesidad de administrar máquinas virtuales o clústeres.

## Health checks en Cloud Run

Cloud Run usa **probes** (sondas) para saber si un contenedor ya arrancó y si sigue funcionando bien. Se configuran por contenedor, en el `service.yaml` o con `gcloud`.

#### 1. Startup probe (sonda de arranque)

**Para qué sirve:** indica cuándo el contenedor terminó de arrancar. Mientras no la supere, Cloud Run **no le envía tráfico** y no ejecuta la liveness probe.

- **Tipos:** `TCP`, `HTTP` (HTTP/1) y `gRPC`.
- **Por defecto:** si no configuras ninguna, Cloud Run aplica una **TCP startup probe automática** contra el puerto del contenedor. Esa probe solo comprueba que el puerto esté abierto.
- **Si falla:** la instancia se apaga y se marca como fallida. Si es una revisión nueva, el despliegue falla.
- **Cuándo usarla:** con apps que tardan en arrancar, por ejemplo Java/Spring, apps que cargan modelos de ML o que calientan cachés. Así no se manda tráfico antes de tiempo.

#### 2. Liveness probe (sonda de vida)

**Para qué sirve:** detecta un contenedor que sigue corriendo pero ya no funciona bien (un deadlock, un hilo colgado o una conexión a BD rota).

- **Tipos:** `HTTP` y `gRPC`. TCP no sirve aquí, porque un puerto abierto no garantiza que la app responda bien.
- **Por defecto:** no hay ninguna; tienes que configurarla tú.
- **Si falla:** Cloud Run **reinicia (apaga) la instancia** y crea otra.
- **Cuándo usarla:** en servicios largos donde la app puede quedarse "zombi" sin que el proceso muera.

#### 3. Readiness probe (sonda de disponibilidad)

Es más reciente en Cloud Run (llegó en *preview*). Revisa en la documentación si ya está en GA para tu caso.

- **Para qué sirve:** saca temporalmente una instancia del balanceo de tráfico **sin reiniciarla**, por ejemplo cuando está saturada o pierde una dependencia.
- **Tipos:** `HTTP` y `gRPC`.
