# Scavenger Hunt

EasyWeb ExploitationpicoCTF 2021
## Description

There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:44070/). Can you find it?

## Hints 1

* You should have enough hints to find the files, don't run a brute forcer.

## Solución

Entramos en el link proporcionado y una vez en la pagina, damos clic derecho y seleccionamos ver el código fuente de la página, una vez en el código nos da una pista del inicio de nuestra flag y vamos completando las partes:
###### Primera pista: Here's the first part of the flag: picoCTF{t -->

Para nuestra segunda pista, en el mismo código, en la parte de "[mycss.css](http://mercury.picoctf.net:44070/mycss.css)" y nos da lo siguiente parte de la flag:
###### Segunda pista: CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

Para la tercera pista, en el link que nos proporcionan, al final de su url se agregara "/robots.txt", "http://mercury.picoctf.net:44070/robots.txt" y así nos mostrara la tercera pista:
###### Tercera pista: # Part 3: t_0f_pl4c

En la cuarta pista, en el url que nos dieron le volvemos agregar algo al final en este casi seria un "/.htaccess" "http://mercury.picoctf.net:44070/.htaccess" y nos dara la continuación de la flag:
###### Cuarta pista: # Part 4: 3s_2_lO0k

Y para finalizar nuestra ultima y quinta pista, en nuestro mismo url agregamos al final lo siguiente "/.DS_Store" "http://mercury.picoctf.net:44070/.DS_Store" y así nos da el resultado de nuestra flag.
###### Quinto pista: Part 5: _7a46d25d}

Y juntando todas las pistas en el orden correspondiente nos mostrara la flag final.

### Respuesta: picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}