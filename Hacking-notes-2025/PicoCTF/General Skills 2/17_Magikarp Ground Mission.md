# Magikarp Ground Mission

### Description

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `ee388b88`

Additional details will be available after launching your challenge instance.

| Challenge Endpoints |                                             |
| :-----------------: | :-----------------------------------------: |
|         SSH         | `ssh ctf-player@venus.picoctf.net -p 52944` |
### Hints 

* Finding a cheatsheet for bash would be really helpful!

## Solución

Accedemos a la dirección del enlace con ssh el cual tiene un usuario y una contraseña, después vemos su contenido con un ls, enseguida vamos obteniendo las partes de nuestra respectiva flag y seguimos los pasos para sacar las demás partes de la flag:

```cmd
jazmin@DESKTOP-1CBQJ6D:~/FIS$ ssh ctf-player@venus.picoctf.net -p 52944
ctf-player@venus.picoctf.net's password:
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Mon Feb 17 18:59:33 2025 from 127.0.0.1
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ pwd
/home/ctf-player/drop-in
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  boot  etc   instructions-to-3of3.txt  lib64  mnt  proc  run   srv  tmp  var
bin            dev   home  lib                       media  opt  root  sbin  sys  usr
ctf-player@pico-chall$ cd home/
ctf-player@pico-chall$ ls
ctf-player
ctf-player@pico-chall$ cd ctf-player/
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt
3ca613a1}
ctf-player@pico-chall$ cd home/
-bash: cd: home/: No such file or directory
ctf-player@pico-chall$ cd /
ctf-player@pico-chall$ ls
2of3.flag.txt  boot  etc   instructions-to-3of3.txt  lib64  mnt  proc  run   srv  tmp  var
bin            dev   home  lib                       media  opt  root  sbin  sys  usr
ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ Connection to venus.picoctf.net closed by remote host.
Connection to venus.picoctf.net closed.
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```

### Respuesta: picoCTF{xxsh_0ut_0f_\/\/4t3r_3ca613a1}