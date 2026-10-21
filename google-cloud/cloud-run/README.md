## ¿Qué es cloud Run?

Es una plataforma de computación sin servidores (serverless) de google cloud que permite ejecutar código empaquetado en contenedores de forma automática, sin necesidad de administrar máquinas virtuales o clústeres.


## ¿Qué es un heald check?

Las comprobaciones de estado de Cloud Run se aseguran de que tus instancias de contenedores se ejecuten correctamente y puedan servir tráfico. Con las comprobaciones de estado de Cloud Run, puedes personalizar cuando está listo tu contenedor para recibir solicitudes y cuando se debe considerar que no está en buen estado para que sea necesario reiniciarlo.

## Tipos de Heald Chekcs

#### Startup probe (Comprobadores de inicio)
Las comprobaciones de inicio determinan si el contenedor se a iniciado y está listo para aceptar el tráfico.

- Cuando configuras una comprobación de inicio, las comprobaciones de vivacidad y preparación se inhabilitan hasta que la comprobación de inicio termina que el contenedor se ha iniciado, para evitar interferencias con el inicio del servicio.
- Las sondas de inicio son especialmente útiles si usas las comprobaciones de actividad en contendores que tardan en iniciarse, ya que evitan que los contenedores se cierren prematuramente antes de que estén en funcionamiento.

#### Liveness probe (Compronaciones de vivacidad)
Las comprobaciones de vivacidad determinan si se debe reiniciar un contenedor
- En este caso, reiniciar un contenedor puede aumentar la disponibilidad del servicio en caso haya errores.
- Las sondas de actividad están diseñadas para reiniciar instancias individuales que no se pueden recuperar de ninguna otra forma. Deben usarse principalmente para errores irrecuperables de instancias, como detectar interbloqueo en el que se está ejecutando un servicio, pero no puede avanzar. Puedes requerir una prueba de actividad para cada contenedor mediante políticas de organización.

#### Readiness check (Comprobaciones de preparación)
- Las sondas de disponibilidad determinan cuándo debe servir tráfico una instancia de tu servicio de Cloud Run. Las comprobaciones de disponibilidad empiezan después de que la sonda de inicio del contenedor se haya completado correctamente. Si una instancia no supera su prueba de disponibilidad más allá del valor de umbral de errores que hayas configurado, Cloud Run dejará de enviarle tráfico nuevo. Cloud Run no termina la instancia y envía tráfico de vuelta a la instancia cuando empieza a superar de nuevo la comprobación de disponibilidad.

## Dicionario
- Vivacidad: Es la cualidad de ser viváz, se refiere a la energía, el dinamismo el ingenio o la rapidéz de algo, así como el brillo, la intensidad y el color de las cosas.
- Prematuro: Algo ocurre, se ejecuta, se pública o nace antes del tiempo previsto, de la maduración necesaria o del momento óptimo. 
