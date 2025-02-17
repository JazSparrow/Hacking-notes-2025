# Based

### Description

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

### 1 2 Hints 

* I hear python can convert things.
* It might help to have multiple windows open.

## Solución

En la terminal de linux, ingresamos el comando que se nos proporciona en la descripción, una vez ejecutado nos pide convertir de binario a una palabra en ASCII, una vez convertida a palabra pasa a la siguiente que seria en octal y la volvemos a convertir a ASCII y por ultimo nos pide convertir de Hexa a ASCII de igual forma, una vez ingresado cada resultado de cada conversión, nos imprime nuestra flag: 

![[Pasted image 20250215203934.png]]

### Resultado: picoCTF{learning_about_converting_values_b375bb16}

## Referencias
https://www.traductorbinario.com/
https://gchq.github.io/CyberChef/
