# Secrets

## Description

We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:51754/).

---
## Hints 1

* folders folders folders.

## Solución

Entramos al url proporcionado, una vez ahí, y enseguida vamos al **código fuente** y encontramos 
"[secret/assets/DX1KYM.jpg](view-source:http://saturn.picoctf.net:51754/secret/assets/DX1KYM.jpg)" por lo tanto escribimos **secret** al final del url para descubrir nuestra flag.
```
http://saturn.picoctf.net:51754/secret/
```

Después entramos al **código fuente** y ahí nos muestra [hidden/file.css](view-source:http://saturn.picoctf.net:51754/secret/hidden/file.css) entonces escribimos **hidden** al final del url:
```
http://saturn.picoctf.net:51754/secret/hidden/
```

En el código fuente nos parece **"superhidden/xdfgwd.html"** y agregamos **superhidden** al final del url y por fin nos muestra la página final.
```
http://saturn.picoctf.net:51754/secret/hidden/superhidden/
```

Damos clic derecho y en **ver código fuente** y ahí nos mostrara nuestra flag:
```
# Finally. You found me. But can you see me

# Código Fuente
<!DOCTYPE html> <html> <head> <title></title> <link rel="stylesheet" href="[mycss.css](view-source:http://saturn.picoctf.net:51754/secret/hidden/superhidden/mycss.css)" /> </head> <body> <h1>Finally. You found me. But can you see me</h1> <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_51b260fe}</h3> </body> </html>
```

### Respuesta: picoCTF{succ3ss_@h3n1c@10n_51b260fe}