# shark on wire 2
#### Description

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

#### Hints

* (None)

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta en linux, después abrimos la terminal e ingresamos el siguiente comando para instalar:

`python3 -m pip install scapy`

Enseguida realizamos el siguiente script para poder filtrar cada captura del paquete:

```
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''
for p in packets:
	if UDP in p and p[UDP].dport == 22:
		flag += chr(p[UDP].sport - 5000)
print(flag)
```

Y lo ejecutamos con el siguiente comando:

`python3 exp.py`

Y con esto nos mostrara nuestra respectiva flag.
### Respuesta: PicoCTF{P1LLf3r3d_data_v1a_st3g0}