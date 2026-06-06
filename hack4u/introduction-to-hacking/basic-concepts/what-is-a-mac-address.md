### ¿Qué es una dirección mac?
Es un identificador de 48 bits que corresponde de forma única a una targeta o dispositivo de red se le conoce también como dirección fisica y es única para cada cada dispositivo.
Es como el propio DNI de las personas pero también se puede falsificar
Ver dispositivos contectados a una interfáz de red
```bash
arp-scan -I eth0 --localnet
```

0c:4f:9b:60:03:f1
<code>0c:4f:9b</code> OUI (Organizational Unique Identifier)

Listar direcciones más sobre todo la parte OUI
```bash
macchanger -l
```
