# GET aHEAD

## Description

Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:45028/](http://mercury.picoctf.net:45028/)

## Hints 1 2

* Maybe you have more than 2 choices
* Check out tools like Burpsuite to modify your requests and look at the responses

## Solución

En la terminal de webshell, ingresamos un **curl** y un **-I** para que la flag se muestre solo la flag sin detalles innecesarios, enseguida ingresamos el link y lo modificamos con un **"/index.php"** al final del url y esto nos mostrara nuestra respectiva flag:

```
Jaz_sparrow-picoctf@webshell:~$ curl -I http://mercury.picoctf.net:45028/index.php
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_775f2530}
Content-type: text/html; charset=UTF-8
```

### Respuesta: picoCTF{r3j3ct_th3_du4l1ty_775f2530}