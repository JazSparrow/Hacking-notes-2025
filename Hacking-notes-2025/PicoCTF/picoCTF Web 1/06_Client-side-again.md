# Client-side-again
## Description

Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/60786/` ([link](https://jupiter.challenges.picoctf.org/problem/60786/)) or http://jupiter.challenges.picoctf.org:60786

## Hints 1

* What is obfuscation?

## Solución
Entramos en el link proporcionado y abrimos el código fuente de la página, copiamos la 'var _0x5a46' que aparece en el código en la columna 10 y lo ponemos en una terminal de javascript y hace la conversión para que nos proporcione un 'var _0x5a46' con la pista de la flag y lo seleccionamos de la siguiente manera.

![[Pasted image 20250324210213.png]]

Una vez copiado el 'var', lo pegamos en un console del código de fuente, cambiamos el var a 'var f =' y ubicamos en que posición están las posibles pistas de nuestra flag y nos muestra el resultado:

![[Pasted image 20250324132444.png]]
### Respuesta: picoCTF{not_this_again_ef49bf}

### Referencias:
http://jsnice.org/