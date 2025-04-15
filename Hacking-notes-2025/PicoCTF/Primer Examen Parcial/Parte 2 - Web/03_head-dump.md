# head-dump

## Description

Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag. The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden. The website is running [picoCTF News](http://verbal-sleep.picoctf.net:59695/).

## Hints

* Explore backend development with us.
* The head was dumped.

## Solución

Entramos al link proporcionado y una vez ahí, vamos a las letras en azul de **#API documentation** y damos clic, nos vamos a la parte de **get_heapdump** pero si se quiere ir mas rápido damos clic en el siguiente link el cual nos llevara en automático: `http://verbal-sleep.picoctf.net:59695/api-docs/#/Diagnosing/get_heapdump`
Después descargamos el archivo que se nos indica.
Una vez echo esto abrimos el archivo con algún editor de texto, en este caso lo haremos con **visual studio code** y con `crtl f`, nos abre la lupa para buscar la palabra clave de **pico** y con esto nos muestra nuestra respectiva flag:

![[Pasted image 20250413221658.png]]
### Respuesta: picoCTF{Pat!3nt_15_Th3_K3y_63fa652c}