# flags are stepic

#### Description

A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their message Try it [here](http://standard-pizzas.picoctf.net:62840/)!

---
#### Hints

In the country that doesn't exist, the flag persists

## Solución

Primero iniciamos nuestra instancia para los datos que necesitaremos.
Después ingresamos al link que se nos proporciona, enseguida buscamos la bandera llamada: 
* `Upanzi, Republic`

Y descargamos la imagen y la ubicamos en nuestra carpeta de linux.

![[upz.png]] 
Una vez en nuestra terminal instalamos el `stepic` ya que lo utilizaremos para encontrar nuestra flag dentro de la imagen:

`sudo apt install stepic`

Y por ultimo aplicamos un `stepic -d -i upz.png` y con esto nos mostrara nuestra respectiva flag.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ file upz.png
upz.png: PNG image data, 14173 x 10630, 8-bit/color RGBA, non-interlaced
jazmin@DESKTOP-1CBQJ6D:~/FSI$ strings upz.png | grep pico
jazmin@DESKTOP-1CBQJ6D:~/FSI$ stepic

Command 'stepic' not found, but can be installed with:

sudo apt install stepic

jazmin@DESKTOP-1CBQJ6D:~/FSI$ sudo apt install stepic
[sudo] password for jazmin:
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following NEW packages will be installed:
  stepic
0 upgraded, 1 newly installed, 0 to remove and 25 not upgraded.
Need to get 8876 B of archives.
After this operation, 38.9 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu focal/universe amd64 stepic all 0.4.1-1 [8876 B]
Fetched 8876 B in 0s (18.5 kB/s)
Selecting previously unselected package stepic.
(Reading database ... 85989 files and directories currently installed.)
Preparing to unpack .../stepic_0.4.1-1_all.deb ...
Unpacking stepic (0.4.1-1) ...
Setting up stepic (0.4.1-1) ...
Processing triggers for man-db (2.9.1-1) ...
jazmin@DESKTOP-1CBQJ6D:~/FSI$ stepic
Usage: stepic [options]

choose either encode or decode
jazmin@DESKTOP-1CBQJ6D:~/FSI$ stepic -d -i upz.png
/usr/lib/python3/dist-packages/PIL/Image.py:2763: DecompressionBombWarning: Image size (150658990 pixels) exceeds limit of 89478485 pixels, could be decompression bomb DOS attack.
  warnings.warn(
picoCTF{fl4g_h45_fl4ga664459a}jazmin@DESKTOP-1CBQJ6D:~/FSI$
```

### Respuesta: picoCTF{fl4g_h45_fl4ga664459a}