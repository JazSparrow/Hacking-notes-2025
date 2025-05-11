# hideme

#### Description

Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/258/flag.png).

#### Hints

* (None)

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Ingresamos a nuestra terminal de linux e ingresamos en las siguientes  direcciones de carpeta para identificar en cuales carpetas entrar y hacer que la imagen nos muestre la bandera:

* `cd _flag.png.extracted`
* `cd secret`

y después en la ultima carpeta ubicamos nuestra flag en imagen, por lo tanto instalamos `lrzsz` con el siguiente comando:

Y aplicamos un `sz flg.png` y con esto nos abrirá nuestra imagen con la flag dentro.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme$ binwalk flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2876, uncompressed size: 3029, name: secret/flag.png
42915         0xA7A3          End of Zip archive, footer length: 22

jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2876, uncompressed size: 3029, name: secret/flag.png
42915         0xA7A3          End of Zip archive, footer length: 22

jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme$ ls
_flag.png.extracted  flag.png  flag.png:Zone.Identifier
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme$ cd _flag.png.extracted
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme/_flag.png.extracted$ ls
29  29.zlib  9B3B.zip  secret
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme/_flag.png.extracted$ cd secret
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme/_flag.png.extracted/secret$ ls
flag.png
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme/_flag.png.extracted/secret$ sz flg.png

Command 'sz' not found, but can be installed with:

sudo apt install lrzsz

jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme/_flag.png.extracted/secret$ sudo apt install lrzsz
[sudo] password for jazmin:
Reading package lists... Done
Building dependency tree
Reading state information... Done
Suggested packages:
  minicom
The following NEW packages will be installed:
  lrzsz
0 upgraded, 1 newly installed, 0 to remove and 25 not upgraded.
Need to get 74.8 kB of archives.
After this operation, 531 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu focal/universe amd64 lrzsz amd64 0.12.21-10 [74.8 kB]
Fetched 74.8 kB in 1s (66.2 kB/s)
Selecting previously unselected package lrzsz.
(Reading database ... 86001 files and directories currently installed.)
Preparing to unpack .../lrzsz_0.12.21-10_amd64.deb ...
Unpacking lrzsz (0.12.21-10) ...
Setting up lrzsz (0.12.21-10) ...
Processing triggers for man-db (2.9.1-1) ...
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme/_flag.png.extracted/secret$ sz flg.png
jazmin@DESKTOP-1CBQJ6D:~/FSI/hideme/_flag.png.extracted/secret$
```


![[flag.png]]

### Respuesta: picoCTF{Hiddinng_An_imag3_within_@n_ima9e_d55982e8}