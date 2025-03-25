# picobrowser

## Description

This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921

## Hints 1

* You don't need to download a new web browser

## Solución
Abrimos la terminal webshell e ingresamos un curl y un -s para que se presente mejor la flag, enseguida ingresamos el link modificado con un '/flag' al final del url, después agregamos un usuario llamado picobrowser y un grep pico para que nos muestre nuestra respectiva flag.

```
Jaz_sparrow-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent: picobrowser" | grep pico
         <!-- <strong>Title</strong> --> picobrowser!
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}</code></p>
Jaz_sparrow-picoctf@webshell:~$ 
```

### Respuesta: picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}
