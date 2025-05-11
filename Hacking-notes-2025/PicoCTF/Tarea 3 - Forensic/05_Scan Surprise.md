# Scan Surprise

#### Description

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/3/challenge.zip)

The same files are accessible via SSH here: `ssh -p 56374 ctf-player@atlas.picoctf.net` Using the password `6dd28e9b`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

#### Hints

* QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
* Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11.
* If you don't have access to a phone, you can also use zbar-tools to convert an image to text.

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Enseguida iniciamos nuestra instancia para los datos que necesitaremos.

Ingresamos a nuestra terminal de linux y pegamos el ssh de nuestra instancia y la contraseña.

Una vez dentro nos mostrara una imagen de qr, entonces nos damos cuenta de que dentro hay una flag y aplicamos un `zbarimg` y nos mostrara nuestra respectiva flag.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI/Scan$ ssh -p 56374 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password:

































ctf-player@challenge:~/drop-in$ ls
flag.png
ctf-player@challenge:~/drop-in$ zbarimg flag.png
Connection Error (Failed to connect to socket /var/run/dbus/system_bus_socket: No such file or directory)
Connection Null
QR-Code:picoCTF{p33k_@_b00_a81f0a35}
scanned 1 barcode symbols from 1 images in 0 seconds

ctf-player@challenge:~/drop-in$ Connection to atlas.picoctf.net closed by remote host.
Connection to atlas.picoctf.net closed.
jazmin@DESKTOP-1CBQJ6D:~/FSI/Scan$
```

![[Pasted image 20250511013138.png]]

### Respuesta: picoCTF{p33k_@_b00_a81f0a35}