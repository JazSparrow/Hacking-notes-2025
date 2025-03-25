## Insp3ct0r

### Descripcion

Kishor Balan tipped us off that the following code may need inspection: `https://jupiter.challenges.picoctf.org/problem/9670/` ([link](https://jupiter.challenges.picoctf.org/problem/9670/)) or http://jupiter.challenges.picoctf.org:9670

### Hints 1 2

* How do you inspect web code on a browser?
* There's 3 parts

## Solución

Entramos en el link proporcionado y una vez en la pagina, damos clic derecho y seleccionamos ver el código fuente de la página, una vez en el código nos da una pista del inicio de nuestra flag y vamos completando las partes:
###### Primera pista: <!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->

Para nuestra segunda pista, en el mismo código, en la parte de "[mycss.css](https://jupiter.challenges.picoctf.org/problem/9670/mycss.css)" y nos da lo siguiente de la flag:
###### Segunda pista: /* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */

Para completar la flag, damos clic en el código en la parte de "[myjs.js](https://jupiter.challenges.picoctf.org/problem/9670/myjs.js)" y nos muestra la ultima pista de la flag
###### Tercera pista: /* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?2e7b23e3} */

### Respuesta: picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}