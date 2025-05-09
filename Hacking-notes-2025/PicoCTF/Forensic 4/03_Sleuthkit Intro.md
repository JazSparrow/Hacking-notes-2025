# Sleuthkit Intro

#### Description

Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory. [Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz) Access checker program: `nc saturn.picoctf.net 57771`

#### Hints

* (None)

## Solución

Primeramente descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Enseguida descomprimimos el archivo que es una imagen con el siguiente comando:

`gzip -d disk.img.gz`

Después aplicamos un mmls para ver las particiones del archivo con el siguiente comando:

`mmls disk.img`

Después entramos a nuestra instancia: 

`nc saturn.picoctf.net 57771`

Después pregunta por la longitud y la respuesta es la ultima partición que viene en el comando de mmls:

`202752`

y una vez ingresado eso nos muestra nuestra respectiva flag.

## Terminal de ejemplo:
```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ ls -lah disk.img.gz
-rw-r--r-- 1 jazmin jazmin 29M May  7 12:48 disk.img.gz
jazmin@DESKTOP-1CBQJ6D:~/FSI$ gzip -d disk.img.gz
jazmin@DESKTOP-1CBQJ6D:~/FSI$
jazmin@DESKTOP-1CBQJ6D:~/FSI$ gzip -d disk.img.gz
gzip: disk.img.gz: No such file or directory
jazmin@DESKTOP-1CBQJ6D:~/FSI$
jazmin@DESKTOP-1CBQJ6D:~/FSI$ ls -lah disk.img
-rw-r--r-- 1 jazmin jazmin 100M May  7 12:48 disk.img
jazmin@DESKTOP-1CBQJ6D:~/FSI$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
jazmin@DESKTOP-1CBQJ6D:~/FSI$ nc saturn.picoctf.net 57771
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752
202752
Great work!
picoCTF{mm15_f7w!}
```

### Respuesta: picoCTF{mm15_f7w!}