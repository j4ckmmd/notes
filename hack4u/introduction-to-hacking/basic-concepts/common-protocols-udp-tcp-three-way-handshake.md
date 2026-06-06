### Protocolos comunes (UDP, TCP) y el famoso Three-Way Hanfshake

**TCP:** Es un protoco oriendato a conexión, la gran mayoría de dispositivos lo utilizan para comunicarse a travéz de internet. Es uno de los principales protocolos en redes TCP.

**UDP:** Proporciona verificación de errores, además de garantizar la entrega de datos y que los paquetes se entreguen en el orden en el que fueron enviados. Por el contrario UDP es un protocolo sin conexión. A diferencia del protocolo TCP no garantiza la entrega de datos ni verifica los errores, el protocolo UDP envía continuamente datos al destinatario normalmente pero si comprobar que este los reciba. Normalmente cuando hablamos de TCP hablamos del famoso SYN > SYN ACK > ACK.

Ejecutar wireshark en background
```bash
wireshark &> /dev/null & disown
```
Estaremos motinorizando la loopback
Ponerse en escucha con Netcat:
```bash
nc -nlvp 4646 
```
Conectarse con Netcat
```bash
nc 192.168.18.16 4646
```
Observamos los tres pasos que se ejecutan al momento de entablar una conexión por TCP SYN > SYN ACK > ACK.
<img width="1735" height="122" alt="image" src="https://github.com/user-attachments/assets/d2486b11-e6a7-450c-9610-c7a9bba89ab9" />

Hay 65535 puertos en total

Puertos más comunes
TCP 
---------------
- 21 -> FTP => Trasferir archivos entre otras cosas
- 22 -> SSH => Para acceder a una maquina con un usuario y contraseña
- 23 -> Telnet => Es un protocolo de red que nos permite acceder a otra máquina para manejarla remotamente como si estuvieramos sentados delante de ella, bastane te común.
- 25 => SMTP => (Simple Mail Transfer Protocol) y es un protocolo de red utilizado en el envio y recepción de correos electrónicos.
- 53 -> DNS
- 80 -> HTTP => Páginas web
- 443 -> HTTPS => Páginas web con candadito
- 110 -> (POP3)
- 139, 445 -> (SMB) => Es bastante común encontrarnos este protocolo en redes internas de la empresa, donde te encuentras con recursos compartidos a nivel de red o con una versión un tanto antigua si la acompaña una maquina antigua. El SMB hace mucho daño en redes internas de cara a una auditoría.
- 143 -> (IMAP)

UDP
---------------
- 53 -> (DNS)
- 69 -> (TFTP) =>
- 161 -> (SNMP) => Nos permite recolectar información privilegiada de la máquina en caso de que la comunity string sea predecible o que sea típica rollo public, private y demás.
