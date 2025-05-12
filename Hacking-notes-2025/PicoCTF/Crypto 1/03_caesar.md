# caesar

#### Description

Decrypt this [message](https://jupiter.challenges.picoctf.org/static/6385b895dcb30c74dbd1f0ea271e3563/ciphertext).

#### Hints

* caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

## Solución

Primero descargamos el archivo que nos aparece en nuestra descripción.

Enseguida lo ubicamos en nuestra carpeta de linux, después ingresamos a nuestra terminal de ubuntu y aplicamos un `cat` al archivo `ciphertext` y copiamos el contenido de los entre paréntesis.

Después nos dirigimos al link de **Cyberchef** y en **Recipe** seleccionamos `ROT13` y que estén habilitadas las dos palomitas y en **Amount** escribimos 25 y pegamos el `dspttjohuifsvcjdpoabrkttds` y nos mostrará el nuevo contenido de nuestra flag.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd caesar
jazmin@DESKTOP-1CBQJ6D:~/FSI/caesar$ cat ciphertext
picoCTF{dspttjohuifsvcjdpoabrkttds}jazmin@DESKTOP-1CBQJ6D:~/FSI/caesar$
```

![[Pasted image 20250512144416.png]]

### Respuesta: picoCTF{crossingtherubiconzaqjsscr}
### Referencias

- https://gchq.github.io/CyberChef/