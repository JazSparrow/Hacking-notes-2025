# WebDecode

## Description

Do you know how to use the web inspector? 
Start searching [here](http://titan.picoctf.net:54177/) to find the flag

---
## Hints 1 2

* Use the web inspector on other files included by the web page.
* The flag may or may not be encoded.

## Solución

Iniciamos nuestra instancia y entramos al sitio web proporcionado, una vez ahí, damos clic en el botón **about** damos clic derecho con el mouse sobre el mensaje y seleccionamos **Inspeccionar**, una vez ahí buscamos el texto escondido y lo copiamos, como se observa en la imagen:

![[Pasted image 20250401231430.png]]

Una vez copiado el texto, lo ponemos en **Cyberchef** en **Recipe** y como resultado nos dara nuestra flag correspondiente:

![[Pasted image 20250401231134.png]]

### Respuesta: picoCTF{web_succ3ssfully_d3c0ded_07b91c79}

## Referencias:
https://gchq.github.io/CyberChef/