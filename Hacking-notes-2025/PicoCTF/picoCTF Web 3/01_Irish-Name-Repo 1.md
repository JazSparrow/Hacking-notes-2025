# Irish-Name-Repo 1
## Description

There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## Hints 1 2

* There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

* Try to think about how the website verifies your login.

## Solución

Ingresamos al link proporcionado y nos pide un usuario y una contraseña, después de hacer varios intentos, procedemos a dar clic derecho y seleccionamos **inspeccionar** y volvemos a dar clic derecho pero esta vez sobre el botón de **"login"** y en la línea seleccionada y cambiamos algunas cosas y debe quedar de la siguiente manera:
![[Pasted image 20250331215938.png]]
Una vez realizado esto, damos enter y con esto nos muestra nuestra respectiva flag:
![[Pasted image 20250331122329.png]]

### Respuesta: picoCTF{s0m3_SQL_fb3fe2ad}