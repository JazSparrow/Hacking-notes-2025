# Roboto Sans

## Description

The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:62762/) out.

---
## Hints

* (None)

## Solución

Iniciamos nuestra instancia y entramos al sitio web proporcionado, una vez ahí, en el link escribimos hasta el final **robots.txt** quedando de la siguiente manera: http://saturn.picoctf.net:62762/robots.txt, después no aparecerá un texto y de este vamos a decodificar la segunda línea:

```
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
**anMvbXlmaWxlLnR4dA==**
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```

Un vez en la página pegamos el texto para decodificar y nos muestra un .txt:
![[Pasted image 20250402180352.png]]

Copiamos el **js/myfile.txt** y nos queda de la siguiente manera: http://saturn.picoctf.net:62762/js/myfile.txt, y así nos mostrara nuestra respectiva flag.
### Respuesta: picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}

## Referencias:
https://www.base64decode.org/