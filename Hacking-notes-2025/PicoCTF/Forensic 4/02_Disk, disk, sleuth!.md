# Disk, disk, sleuth!

#### Description

Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/f63e4eba644c99e92324b65cbd875db6/dds1-alpine.flag.img.gz)

#### Hints

* Have you ever used `file` to determine what a file was?
* Relevant terminal-fu in picoGym: https://play.picoctf.org/practice/challenge/85
* Mastering this terminal-fu would enable you to find the flag in a single command: https://play.picoctf.org/practice/challenge/48
* Using your own computer, you could use qemu to boot from this disk!

## Solución

Primeramente descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

 Después vemos que tipo de archivo es con el siguiente comando:

`file dds1-alpine.flag.img.gz`

Enseguida descomprimimos el archivo ya que es un zip con el siguiente comando:

`unzip dds1-alpine.flag.img`

Dentro de la carpeta descomprimida se encuentra una imagen en el cual dentro se observa la flag, entonces aplicamos un `srch_strings` y un `grep picoCTF{.*}`

`srch_strings dds1-alpine.flag.img | grep picoCTF{.*}`

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ ls -lah dds1-alpine.flag.img
total 129M
drwxr-xr-x  2 jazmin jazmin 4.0K May  7 12:40 .
drwxr-xr-x 25 jazmin jazmin  32K May  7 12:40 ..
-rw-r--r--  1 jazmin jazmin 128M Mar 15  2021 dds1-alpine.flag.img
jazmin@DESKTOP-1CBQJ6D:~/FSI$ gzip -d dds1-alpine.flag.img.gz
gzip: dds1-alpine.flag.img already exists; do you wish to overwrite (y or n)? y
gzip: dds1-alpine.flag.img: Is a directory
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd dds1-alpine.flag.img/
jazmin@DESKTOP-1CBQJ6D:~/FSI/dds1-alpine.flag.img$ srch_strings dds1-alpine.flag.img | grep pico
ffffffff81399ccf t pirq_pico_get
ffffffff81399cee t pirq_pico_set
ffffffff820adb46 t pico_router_probe
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_ad5c96c0}
```

### Respuesta: picoCTF{f0r3ns1c4t0r_n30phyt3_ad5c96c0}