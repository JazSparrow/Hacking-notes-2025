# interencdec

#### Description

Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/2/enc_flag).

#### Hints

* Engaging in various decoding processes is of utmost importance

## Solución

Primero descargamos nuestro archivo y lo colocamos en nuestra carpeta ubuntu
Una vez ahí ingresamos los siguientes comandos:
* `cat enc_flag`
* `cat enc_flag | base64 -d`

En el comando anterior nos sale un encriptado que es el que vamos a pegar a continuación y a aplicar un echo en base64.
* `echo d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ== | base64 -d`

Y copiamos lo que vendría siendo la flag encriptada.

Después nos dirigimos al link de **Cyberchef** en **Recipe** seleccionamos `ROT13` y que estén habilitadas las dos palomitas y en **Amount** escribimos 19 y nos mostrara nuestra respectiva flag.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI/waves$ mkdir inter
jazmin@DESKTOP-1CBQJ6D:~/FSI/waves$ cd inter
jazmin@DESKTOP-1CBQJ6D:~/FSI/waves/inter$ ls
 enc_flag  'enc_flag(1):Zone.Identifier'
jazmin@DESKTOP-1CBQJ6D:~/FSI/waves/inter$ cat enc_flag
YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclh6YzRNalV3YUcxcWZRPT0nCg==
jazmin@DESKTOP-1CBQJ6D:~/FSI/waves/inter$ cat enc_flag | base64 -d
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ=='
jazmin@DESKTOP-1CBQJ6D:~/FSI/waves/inter$ echo d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrXzc4MjUwaG1qfQ== | base64 -d
wpjvJAM{jhlzhy_k3jy9wa3k_78250hmj}jazmin@DESKTOP-1CBQJ6D:~/FSI/waves/inter$
```

![[Pasted image 20250512162523.png]]

### Respuesta: picoCTF{caesar_d3cr9pt3d_78250afc}