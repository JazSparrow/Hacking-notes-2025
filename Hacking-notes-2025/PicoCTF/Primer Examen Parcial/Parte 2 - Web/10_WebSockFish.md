# WebSockFish

## Description

Can you win in a convincing manner against this chess bot? He won't go easy on you! You can find the challenge [here](http://verbal-sleep.picoctf.net:60291/).

## Hints

* Try understanding the code and how the websocket client is interacting with the server

## Solución

Primero entramos al link proporcionado, una vez ahí observamos que hay un juego de ajedrez pero sería difícil ganar, entonces damos clic derecho para ver su **código fuente**, una vez ahí buscamos esta línea de código que será clave para los comandos que pondremos:

```
if (event.data.includes("mate")) {
message = "mate " + parseInt(splitString[9]); 
} else { 
message = "eval " + parseInt(splitString[9]); } 
sendMessage(message); }
```

Un vez identificadas las palabras clave, pasamos a dar clic derecho en **Inspeccionar** y nos vamos a la parte de **Consola**, allí ingresamos los siguientes comandos:
* sendMessage("mate 1")
* sendMessage("mate 2")
* sendMessage("mate 10000000000000000000")
* sendMessage("mate -10000000000000000000")
* sendMessage("mate -100000000000000000000000000000000000000")
* sendMessage("mate -100000000000000000000000000000000000000")
* sendMessage("mate -100000000000000000000000000000000000000")
* sendMessage("mate -100000000000000000000000000000000000000000000000000")
* sendMessage("eval -100000000000000000000000000000000000000000000000000")

![[Pasted image 20250414211906.png]]

Y en el tablero de ajedrez nos muestra nuestra respectiva flag:
![[Pasted image 20250414211930.png]]

### Respuesta: picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_dc1dbff7}