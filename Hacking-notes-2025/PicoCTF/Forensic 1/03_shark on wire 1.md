# shark on wire 1
## Description

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Hints 1 2

* Try using a tool like Wireshark
* What are streams?

## Solución

Para este reto utilizamos el programa **WireShark**
En nuestra terminal de Ubuntu ingresamos el siguiente comando que nos abrirá el paquete de captura en el programa.
```
wireshark capture.pcap
```

En el programa d **WireShark**, buscaremos en el **udp** y después de pasar varias veces en el udp nos mostrara nuestra flag.

### Respuesta: picoCTF{StaT31355_636f6e6e}

