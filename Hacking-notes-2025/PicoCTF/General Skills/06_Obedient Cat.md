# Obedient Cat
## Description

This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag).

## 1 2 3 Hints 

* Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.

* To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag`

* $ man cat

## Solución

Se descarga el archivo adjunto para ubicarlo en la carpeta de linux.
Se utilizara la terminal linux para abrir el contenido del archivo, en el cual se utilizara el siguiente comando de cat flag, y nos imprime nuestra flag:

```
jazmin@DESKTOP-1CBQJ6D:~/jazmin$ cat flag  -A
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}$
jazmin@DESKTOP-1CBQJ6D:~/jazmin$
```

#### Respuesta: picoCTF{s4n1ty_v3r1f13d_4a2b35fd}