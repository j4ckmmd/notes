### ¿Qué es una IP?
Es una etiqueta numérica que identfica de manera lógica y gerarquica a una interfáz en la red de un dispositivo el protocolo de internet
```bash
# Ver dirección ip
hostname -I 
```
Una IP tiene cuatro octectos es decir se divide en 4 partes de 8 bits en total 32 bits
```bash
# Ip 192.168.111.42
echo "$(echo "obase=2;192" | bc).168.111.42"
ouput: 11000000.168.111.42
       8bits.8bits.8bits.8bits
```
```bash
# Dirección ip en binario
echo "$(echo "obase=2; 192" | bc).$(echo "obase=2; 168" | bc).$(echo "obase=2; 111" | bc).$(echo "obase=2; 42" | bc)"
ouput: 11000000.10101000.1101111.101010
```

```bash
# Total de direcciones IPv4 disponibles
echo "2^32" | bc
ouput: 4294967296
```
Ver habitantes en la tierra
https://countrymeters.info/en/World
