# Operation Oni

#### Description

Download this disk image, find the key and log into the remote machine. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/69/disk.img.gz)
- Remote machine: `ssh -i key_file -p 52069 ctf-player@saturn.picoctf.net`

#### Hints

* (None)

## Solución

Primeramente descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Enseguida descomprimimos el archivo que es una imagen con el siguiente comando:

`gzip disk.img.gz`

Después aplicamos un mmls para ver las particiones del archivo con el siguiente comando:

`mmls disk.img`

Se observa que los archivos se encuentran en la ultima partición y se listaran los archivos con los siguientes comandos:

`fls disk.img -o 206848`

A continuación abrimos el root para ingresar de acceso remoto.

`fls -o 206848 disk.img 470`

Ahora abrimos el archivo .ssh:

`fls -o 206848 disk.img 3916`

Enseguida mandamos el archivo a una key_file:

`icat -o 206848 disk.img 2345 > key_file`

Y para ingresar utilizamos el siguiente comando:

```
icat disk.img -o 206848 2345 > key_file
chmod 600 key_file
ssh -i key_file -p 52069 ctf-player@saturn.picoctf.net
```

Utilizamos un `ls` para visualizar los archivos dentro y aplicamos un `cat` para que nos muestre nuestra respectiva flag:
`cat flag.txt`

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FSI
jazmin@DESKTOP-1CBQJ6D:~/FSI$ mkdir Operationoni
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd Operationoni
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ gzip disk.img.gz
gzip: disk.img.gz already has .gz suffix -- unchanged
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ gzip -d disk.img.gz
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ ls -lah disk.img
-rw-r--r-- 1 jazmin jazmin 230M May  7 13:24 disk.img
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ fls disk.img -o 206848
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 458:        home
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ fls disk.img -o 206848 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ fls disk.img -o 206848 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ icat disk.img -o 206848 2345 > key_file
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ ssh -i key_file -p 52069 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:52069 ([13.59.203.175]:52069)' can't be established.
ECDSA key fingerprint is SHA256:bAr5vzQiLGB7zQsjXlfTNpzZw4qLsrE39u6WXjqMjWA.
Are you sure you want to continue connecting (yes/no/[fingerprint])? y
Please type 'yes', 'no' or the fingerprint: y
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[saturn.picoctf.net]:52069,[13.59.203.175]:52069' (ECDSA) to the list of known hosts.
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for 'key_file' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "key_file": bad permissions
ctf-player@saturn.picoctf.net's password:
Permission denied, please try again.
ctf-player@saturn.picoctf.net's password:
Permission denied, please try again.
ctf-player@saturn.picoctf.net's password:

jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ icat disk.img -o 206848 2345 > key_file
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ chmod 600 key_file
jazmin@DESKTOP-1CBQJ6D:~/FSI/Operationoni$ ssh -i key_file -p 52069 ctf-player@saturn.picoctf.net
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$
ctf-player@challenge:~$
ctf-player@challenge:~$ ^C
ctf-player@challenge:~$
ctf-player@challenge:~$
ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
picoCTF{k3y_5l3u7h_339601ed}ctf-player@challenge:~$
```

### Respuesta: picoCTF{k3y_5l3u7h_339601ed}