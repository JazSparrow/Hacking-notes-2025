# chrono

### Description

How to automate tasks to run at intervals on linux servers?

Additional details will be available after launching your challenge instance.

Use ssh to connect to this server:

```
Server: saturn.picoctf.net
Port: 54513
Username: picoplayer 
Password: H9RmN0m18U
```

### Hints 

(None)

## Solución

Ingresamos nuestra dirección ssh proporcionada, ponemos la contraseña y damos los permisos, aplicamos un `cat /etc/crontab` y nos muestra nuestra flag:

```
jazmin@DESKTOP-1CBQJ6D:~$ ssh picoplayer@saturn.picoctf.net -p 54513
The authenticity of host '[saturn.picoctf.net]:54513 ([13.59.203.175]:54513)' can't be established.
ECDSA key fingerprint is SHA256:CB3YJzZNvPU4q/O98sAgEvAc2flYHI4go64WbfN3u54.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:54513,[13.59.203.175]:54513' (ECDSA) to the list of known hosts.
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

picoplayer@challenge:~$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_d83baed1}
picoplayer@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
jazmin@DESKTOP-1CBQJ6D:~$
```

### Resultado: picoCTF{Sch3DUL7NG_T45K3_L1NUX_d83baed1}