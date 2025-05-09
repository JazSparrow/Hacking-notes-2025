# Sleuthkit Apprentice

#### Description

Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/136/disk.flag.img.gz)

#### Hints

* (None)

## Solución

Primeramente descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Enseguida descomprimimos el archivo que es una imagen con el siguiente comando:

`gzip -d disk.flag.img.gz`

Después aplicamos un mmls para ver las particiones del archivo con el siguiente comando:

`mmls disk.flag.img`

Enseguida buscamos el archivo de la bandera y agregamos el ultimo numero del start con el siguiente comando:
`fls disk.flag.img -o 360448 -r | grep flag`

Por ultimo aplicamos un cat en el archivo y con esto nos mostrara nuestra respectiva flag:

`icat disk.flag.img -o 360448 2371`

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ ls -lah disk.flag.img.gz
-rw-r--r-- 1 jazmin jazmin 46M May  7 12:54 disk.flag.img.gz
jazmin@DESKTOP-1CBQJ6D:~/FSI$ gzip -d disk.flag.img.gz
jazmin@DESKTOP-1CBQJ6D:~/FSI$ gzip -d disk.flag.img
gzip: disk.flag.img: unknown suffix -- ignored
jazmin@DESKTOP-1CBQJ6D:~/FSI$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
jazmin@DESKTOP-1CBQJ6D:~/FSI$ fls disk.flag.img -o 360448 -r
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
+ r/r 23:       group
+ r/r 24:       group-
jazmin@DESKTOP-1CBQJ6D:~/FSI$ icat disk.flag.img -o 360448 2371
picoCTF{by73_5urf3r_3497ae6b}
```

### Respuesta: picoCTF{by73_5urf3r_3497ae6b}

#### Glosario de comandos
* mmls <- Ver particiones
* .fls <- Listar archivos
* .icat <- Mostrar archivo