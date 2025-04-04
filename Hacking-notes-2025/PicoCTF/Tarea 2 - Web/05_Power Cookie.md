# Power Cookie

## Description

Can you get the flag? Go to this [website](http://saturn.picoctf.net:57503/) and see what you can discover.

---
## Hints 1

* Do you know how to modify cookies?

## Solución

En la sección de **Cabeceras**, vamos a la **Cabeceras de la petición (489 B)** 
* Cookie: isAdin=0
Enseguida damos al botón de **Reenviar** y en **nueva petición** ponemos un nuevo nombre y valor, que en este caso seria: 
* Cookie: isAdin=1

![[Pasted image 20250403222314.png]]

Y damos en enviar, después nos dirigimos a **Respuesta** y nos saldra nuestra respectiva flag:
![[Pasted image 20250403223323.png]]
### Respuesta: picoCTF{gr4d3_A_c00k13_5d2505be}