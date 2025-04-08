# So Meta
## Description

Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png).

## Hints 1 2

* What does meta mean in the context of files?
* Ever heard of metadata?

## Solución

Primero instalamos la librería de exiftool:
```
sudo apt install exiftool
```

Después descargamos el archivo que en este caso es una imagen jpg:
```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ wget https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png
--2025-04-07 12:23:36--  https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png                  100%[=================================================>] 106.25K   182KB/s    in 0.6s

2025-04-07 12:23:38 (182 KB/s) - ‘pico_img.png’ saved [108795/108795]
```

Aplicamos un exiftool con el nombre de la imagen y para que nos de la bandera mas directo agregamos un **-Artist** **-filter**:
```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ exiftool pico_img.png -Artist -filter
Artist                          : picoCTF{s0_m3ta_eb36bf44}
Filter                          : Adaptive
```

También se puede usar el siguiente comando el cual nos mostrara de igual manera la bandera:
```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ exiftool pico_img.png
```

### Respuesta: picoCTF{s0_m3ta_eb36bf44}
