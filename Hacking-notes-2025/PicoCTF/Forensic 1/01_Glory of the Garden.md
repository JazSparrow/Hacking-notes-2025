# Glory of the Garden
## Description

This [garden](https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg) contains more than it seems.

## Hints 1

* What is a hex editor?

## Solución

Primero descargamos nuestro archivo que en este caso es una imgaen jpg, enseguida aplicamos un **string -n18** junto con el nombre de la imagen para que nos muestre nuestra respectiva flag: 

```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ strings -n18 garden.jpg
Copyright (c) 1998 Hewlett-Packard Company
IEC http://www.iec.ch
IEC http://www.iec.ch
.IEC 61966-2.1 Default RGB colour space - sRGB
.IEC 61966-2.1 Default RGB colour space - sRGB
,Reference Viewing Condition in IEC61966-2.1
,Reference Viewing Condition in IEC61966-2.1
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
Here is a flag "picoCTF{more_than_m33ts_the_3y3657BaB2C}"
```

### Resultado: picoCTF{more_than_m33ts_the_3y3657BaB2C}
