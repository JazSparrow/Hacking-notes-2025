# Milkslap
#### Description

[🥛](http://mercury.picoctf.net:29522/)

#### Hints

* Look at the problem category

## Solución

Primeramente damos clic en el icono de la leche que nos aparece enseguida nos manda a una imagen en movimiento.

En nuestro navegador agregamos la extensión de la imagen con la cual podremos descargarla:
`mercury.picoctf.net:29522/concat_v.png`

Una vez descargada la imagen, la ubicaremos en nuestra carpeta de linux ubuntu.

Instalamos el zsteg el cual nos ayudara a obtener nuestra flag:
`gem install zsteg`

Después ingresamos el siguiente comando en nuestra terminal de linux y con esto nos mostrara nuestra respectiva flag:
`zsteg -s all concat_v.png`

### Respuesta: PicoCTF{imag3_m4n1pul4t10n_sl4p5}