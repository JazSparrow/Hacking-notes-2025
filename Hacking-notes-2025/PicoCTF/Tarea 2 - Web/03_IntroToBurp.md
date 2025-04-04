# IntroToBurp

#### Description

Try [here](http://titan.picoctf.net:51353/) to find the flag

---
## Hints 1 2

* Try using burpsuite to intercept request to capture the flag.
* Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.

## Solución

Para esta actividad necesitaremos el programa: **Burp Suite Community Edition**, Una vez abierto, , después nos dirigimos a **proxy** después damos clic en **open browser**, enseguida copiamos el link que nos proporcionan al principio y lo pegamos en el navegador que se abre automáticamente, después vamos a **proxy settings** y en la parte de **reponse interception rules**, habilitamos la primera opción, después intentamos poner admin en cada casilla y damos enter, enseguida daremos varias veces al botón **-> forward**, y nos dirige al apartado para ingresar el otp, en este caso pondremos cualquier palabra y después nos dirigimos al **interception is on** y nos muestra el código en la parte de abajo donde se ubica el otp lo modificamos el por otgp y queda de la siguiente manera:
**otp=Holaaaa
`otgp=Holaaaa`

y volvemos a presionar **forward** y en el navegador donde copiamos el link, nos mostrara nuestra respectiva flag:

![[Pasted image 20250403233629.png]]
## Respuesta: picoCTF{#0TP_Bypvss_SuCc3$S_2e80f1fd}

