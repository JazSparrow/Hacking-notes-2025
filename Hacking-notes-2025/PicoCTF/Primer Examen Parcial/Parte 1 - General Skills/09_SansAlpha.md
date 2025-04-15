# SansAlpha

## Description

The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols. `ssh -p 52662 ctf-player@mimas.picoctf.net` 

Use password: `1ad5be0d`

## Hints

* Where can you get some letters?

## Solución

Iniciamos nuestra instancia, abrimos nuestra terminal de ubuntu o el webshell del picoCTF e ingresamos nuestra ssh proporcionada e ingresamos la contraseña.

Una vez dentro, intentamos los siguientes comandos para que nos muestre un encriptado de base64:
* `/*/??????`
* `/*/????64 */*`
* `/*/???[!_]64 */*`
* `/*/???[!_]64 */????.*`

y con el ultimo comando nos mostrara el encriptado de base64, el cual en este caso es: `cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV83NzVhYzEyZH0=`

Salimos del **SansAlpha** y en la terminal ingresamos un: `echo cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV83NzVhYzEyZH0= | base64 -d`
 para desencriptar de la base64 para que nos muestre nuestra respectiva flag.

## Terminal de ejemplo

```
jazmin@DESKTOP-1CBQJ6D:~$ ssh -p 52662 ctf-player@mimas.picoctf.net
The authenticity of host '[mimas.picoctf.net]:52662 ([52.15.88.75]:52662)' can't be established.
ECDSA key fingerprint is SHA256:5rS4L0YbD+igsLhyOOBACWOhhxzoxbv5MOee+i2HKSg.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[mimas.picoctf.net]:52662,[52.15.88.75]:52662' (ECDSA) to the list of known hosts.
ctf-player@mimas.picoctf.net's password:
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1016-aws x86_64)

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

SansAlpha$ /*/??????
/bin/base32: extra operand ‘/bin/base64’
Try '/bin/base32 --help' for more information.

SansAlpha$ /*/????64 */*
/bin/base64: extra operand ‘/bin/x86_64’
Try '/bin/base64 --help' for more information.

SansAlpha$ /*/???[!_]64 */*
/bin/base64: extra operand ‘blargh/flag.txt’
Try '/bin/base64 --help' for more information.

SansAlpha$ /*/???[!_]64 */????.*
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV83NzVhYzEyZH0=

SansAlpha$ exit
Connection to mimas.picoctf.net closed.
jazmin@DESKTOP-1CBQJ6D:~$ echo cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV83NzVhYzEyZH0= | base64 -d
return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_775ac12d}jazmin@DESKTOP-1CBQJ6D:~$
```

### Respuesta: picoCTF{7h15_mu171v3r53_15_m4dn355_775ac12d}