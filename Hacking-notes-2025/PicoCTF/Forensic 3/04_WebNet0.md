# WebNet0

#### Description

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

#### Hints

* Try using a tool like Wireshark.
* How can you decrypt the TLS stream?

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux, enseguida nos dirigimos a la terminal e ingresamos el siguiente comando que nos dirigirá al **WireShark** en el cual nos ayudara a resolver el reto:

`wireshark capture.pcap &`

Un vez ahí, seleccionamos el paquete 6 y con el clic derecho seleccionamos `Follow` y `TLS Stream`.

Después nos dirigimos al paquete 34 y con el clic derecho nuevamente seleccionamos `Follow` y `TLS Stream`.

Enseguida descargamos la llave privada, nos dirigimos a `Edit` y a `Preferences`, enseguida de eso vamos a `Protocols` y buscamos `TLS` y nos da la opción de subir una llave y ahí importamos nuestro archivo llamado `picopico.key` y una vez subido se pone en verde algunos y esto significa que se desencripta.

Después de eso nos dirigimos al paquete 13 y con el clic derecho seleccionamos `Follow` y `TLS Stream`.

Se realizara una búsqueda en `Edit` y a `Find Next` y seleccionamos `Packet Details`, `Strings` y escribimos en la barra de búsqueda: `PicoCTF` y con eso nos aparecerá nuestra respectiva flag.

![[Pasted image 20250430202733.png]]

### Respuesta: picoCTF{nongshim.shrimp.crackers}
