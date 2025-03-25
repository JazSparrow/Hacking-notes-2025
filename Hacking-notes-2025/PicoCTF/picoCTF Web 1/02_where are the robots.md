# where are the robots

## Description

Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/36474/` ([link](https://jupiter.challenges.picoctf.org/problem/36474/)) or http://jupiter.challenges.picoctf.org:36474

## Hints 1

* What part of the website could tell you where the creator doesn't want you to look?

## Solución

Ingresamos al link proporcionado y al final del url agregamos robots.txt de la siguiente manera: https://jupiter.challenges.picoctf.org/problem/36474/robots.txt y de aquí nos muestra un texto el cual dice que no accedamos:
```
User-agent: *
Disallow: /477ce.html
```
A lo cual copiamos el texto del Disallow al final del url como anteriormente se hizo, por lo cual nuestro link queda de la siguiente manera: https://jupiter.challenges.picoctf.org/problem/36474/477ce.html y con esto nos da nuestra bandera:

![[Pasted image 20250324122444.png]]
### Respuesta: picoCTF{ca1cu1at1ng_Mach1n3s_477ce}