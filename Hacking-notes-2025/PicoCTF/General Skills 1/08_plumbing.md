# plumbing

## Description

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.

## 1 2 Hints 

* Remember the flag format is picoCTF{XXXX}
* What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solución

Cuando se ejecuta el comando de nc nos muestra que no se encuentra ninguna bandera.

```
Jaz_sparrow-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291

I don't think this is a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
Again, I really don't think this is a flag
This is defintely not a flag
This is defintely not a flag
Again, I really don't think this is a flag
I don't think this is a flag either
I don't think this is a flag either
Again, I really don't think this is a flag
Not a flag either
I don't think this is a flag either
This is defintely not a flag
This is defintely not a flag
Not a flag either
Not a flag either
Not a flag either
Again, I really don't think this is a flag
This is defintely not a flag
```

Por lo tanto para poder resolverlo se necesita de una salida grep, al ejecutar el comando nos da el resultado para la bandera:

```
Jaz_sparrow-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | grep pico
picoCTF{digital_plumb3r_ea8bfec7}
```
#### Respuesta: picoCTF{digital_plumb3r_ea8bfec7}
