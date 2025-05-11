# Ph4nt0m 1ntrud3r

#### Description

A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/3fe089c41615b9413666bedca922e07bf6ad8894a3dabd2737735143ad2396cf/myNetworkTraffic.pcap) and try to get the flag.

#### Hints

* Filter your packets to narrow down your search.
* Attacks were done in timely manner.
* Time is essential

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Ingresamos a nuestra terminal de linux e ingresamos el siguiente comando para abrir el wireshark:
wireshark myNetworkTraffic.pcap

Una vez dentro habrá 22 líneas y desde la primera iremos a la parte de Flags, y mas abajo nos aparece TPC payload (4 bytes) y Retransmited TCP segment  data (4 bytes), iremos variando entre ambos y daremos clic derecho y seleccionamos Show Packet Bytes... una vez dentro nos aparecerá una decodificación en ASCII y la seleccionamos y la pegamos en el cyberchef entonces seleccionamos from base64 y nos ira transformando nuestra flag.

![[Pasted image 20250510222308.png]]

![[Pasted image 20250510223947.png]]

**NOTA IMPORTANTE: Cada flag es diferente, se debe buscar línea por línea hasta encontrar los TCP segment data, se puede cambiar para decodificar el ASCII a base64 directamente pero también se puede usar el cyberchef para una mejor referencia y orden en la bandera, como se observa en la siguiente imagen.**

![[Pasted image 20250510222524.png]]

### Respuesta: picoCTF{1t_w4snt_th4t_34sy_tbh_4r_966d0bfb}

### Referencias

- https://gchq.github.io/CyberChef/