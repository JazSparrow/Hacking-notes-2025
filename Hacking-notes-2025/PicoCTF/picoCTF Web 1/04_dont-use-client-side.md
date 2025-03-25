# dont-use-client-side

## Description

Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/29835/` ([link](https://jupiter.challenges.picoctf.org/problem/29835/)) or http://jupiter.challenges.picoctf.org:29835

## Hints 1

* Never trust the client

## Solución

Entramos al link proporcionado y una vez intentado varios usuarios y contraseñas, nos vamos al código fuente y nos muestra el siguiente código:

```
|<script type="text/javascript">|
||function verify() {|
||checkpass = document.getElementById("pass").value;|
||split = 4;|
||if (checkpass.substring(0, split) == 'pico') {|
||if (checkpass.substring(split*6, split*7) == '723c') {|
||if (checkpass.substring(split, split*2) == 'CTF{') {|
||if (checkpass.substring(split*4, split*5) == 'ts_p') {|
||if (checkpass.substring(split*3, split*4) == 'lien') {|
||if (checkpass.substring(split*5, split*6) == 'lz_7') {|
||if (checkpass.substring(split*2, split*3) == 'no_c') {|
||if (checkpass.substring(split*7, split*8) == 'e}') {|
||alert("Password Verified")|
||}|
||}|
||}|
|||
||}|
||}|
||}|
||}|
||}|
||else {|
||alert("Incorrect password");|
||}|
```

En el cual viene nuestra flag desordenada, a lo cual vamos a seguiremos en orden para acomodar nuestra flag, por ejemplo empezamos del (0, split) y ya nos da una pista de que inicia con 'pico', enseguida nos vamos al segundo que seria: (split, split*2) que nos complementa con 'picoCTF', enseguida pasamos al (split*2, split*3) el cual nos da la continuación de 'picoCTF{no_c}', y así pasamos sucesivamente con cada split en orden de numero y nos completa nuestra respectiva flag.
### Respuesta: picoCTF{no_clients_plz_7723ce}