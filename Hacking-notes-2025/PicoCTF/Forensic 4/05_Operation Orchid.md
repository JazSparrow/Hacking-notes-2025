# Operation Orchid

#### Description

Download this disk image and find the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/214/disk.flag.img.gz)

#### Hints

* (None)

## Solución

Primeramente descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Enseguida descomprimimos el archivo que es una imagen con el siguiente comando:

`gzip -d disk.flag.img.gz`

Después aplicamos un mmls para ver las particiones del archivo con el siguiente comando:

`mmls disk.flag.img`

Enseguida buscamos el archivo de la bandera y agregamos el ultimo numero del start con el siguiente comando:

`fls disk.flag.img -o 411648 -r | grep flag`

Enseguida nos muestra que el archivo esta encriptado  y lo desencriptamos para ver el archivo:

- Primeramente mandamos el icat al archivo de texto flag:

`icat disk.flag.img -o 411648 1782 > flag.txt.enc`

- Después desencriptamos invirtiendo el programa y usaremos -d para desencriptar:

`openssl aes256 -salt -out flag.txt -in flag.txt.enc -k unbreakablepassword1234567 -d`

Y por ultimo aplicamos un `cat` en el flag.txt para que nos muestre nuestra respectiva flag:

`cat flag.txt`

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$
jazmin@DESKTOP-1CBQJ6D:~/FSI$ mkdir Operationchid
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd Operationchid
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ gzip -d disk.flag.img.gz
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ ls -lah disk.flag.img
-rw-r--r-- 1 jazmin jazmin 400M May  7 13:06 disk.flag.img
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ fls disk.flag.img -o 411648
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 460:        home
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ fls disk.flag.img -o 411648 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ icat disk.flag.img -o 411648 472
...S$.ash_historyTflag.txtflag.txt.enc,洞jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ icat disk.flag.img -o 411648 1782
Salted__S+%+Okђ(Ac@]ԣ
ޢȤ7 ؎$'%jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ icat disk.flag.img -o 411648 1782 > flag.txt.enc
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ file flag.txt.enc
flag.txt.enc: openssl enc'd data with salted password
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ icat disk.flag.img -o 411648 1875
touch flag.txt
nano flag.txt
apk get nano
apk --help
apk add nano
nano flag.txt
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ openssl aes256 -salt -d -in flag.txt.enc -out flag.txt -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
140007244326208:error:06065064:digital envelope routines:EVP_DecryptFinal_ex:bad decrypt:../crypto/evp/evp_enc.c:610:
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ ls
disk.flag.img  disk.flag.img.gz:Zone.Identifier  flag.txt  flag.txt.enc
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$ cat flag.txt
picoCTF{h4un71ng_p457_1d02081e}jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationchid$
```

### Respuesta: picoCTF{h4un71ng_p457_1d02081e}