El proceso de enviar una solicitud a un servidor es similar a enviar un paquete por correo, si nos paramos a pensar todos los paquetes que envamos de nuestro lado pasan por unos pocos pasos hasta llegar al destinos final. Estos pasos son a los que llamamos **modelo OSI**

### ¿Qué es el modelo OSI?
Es un estándar para los protocolos de red, ejemplo TCP, UDP

Tipos de capas:

1. Física => Volviendo al ejemplo del correo, la capa física serían las carreteras, es decir el camino que toman los paquetes para llegar al destino, como los cables de cobre o fibra óptica.

2. Enlace de Datos => Esta capa actua como inspector, digamos que observa si el paquete tiene algún defecto en su formato y controla el flujo con el que se envian los paquetes. En esta capa los datos recibidos por el medio físico se verifican para ver si tienen algún error y encaso de tenerlos pues tratar de ver si se puede corregir. De esta forma las capas posteriores pueden asumir una transmisión practicamente pues sin errores.

3. Red => Esta sería como la oficina de correos, se encarga de verificar quién es el destinatario y quién es el remitente del mensaje, en caso de que ayan mensajes para enviar pueden llegar a priorizar cuales se enviarán primero y cuál es la mejor manera de enviar esa carta. Es la capa más activa de las redes especialmente en internet y en esta capa es donde tenemos el direccionamiento IP origen y destino.

4. Transporte => Acá sería como los camiones y los carteros, la capa de trasnporte la que garantiza el envio y la recepción de paquetes provenientes de la capaa 3, gestiona el transporte de los paquetes para garantizar el exito en el envio y en la recepción de datos, protocolos muy comunes de esta capa son TCP y UDP.

5. Sesión => Esta capa es la responsable de establecer y terminar la conexión entre hosts, además de realizar el restablecimiento de sesiones esta capa también brinda cierto soporte como registros de logs y la realización de tareas de seguridad.
   
7. Presentación => Sería la responsable de traducir todos los datos para que la utilize la siguiente capa, la capa de aplicación. Acá tendríamos la conversión de códigos a carácteres, la conversión y comprensión de los datos y en caso que sea necesario el cifrado de los mismos

8. Aplicación => Esta es la última capa del modelo OSI y es la capa para consumir los datos, en esta capa ya podriamos enviar correos electrónicos, enviar archivos, acceder a sitios web, conectarnos de forma remota a otras máquinas entre muchas cosas. En esta capa tendríamos los protocolos más comunes como el HTTP, FTP entre otros. 
