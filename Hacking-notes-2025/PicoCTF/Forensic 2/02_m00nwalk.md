# m00nwalk

#### Description

Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.

#### Hints

* How did pictures from the moon landing get sent back to Earth?
* What is the CMU mascot?, that might help select a RX option

## Solución 

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux, enseguida nos dirigimos a la terminal e ingresamos los siguientes comandos para instalar:

`git clone https://github.com/colaclanth/sstv.git`

`python setup.py install`

Ingresamos este comando para transformar el archivo wav a una imagen png.
`sstv -d message.wav -o flag.png`

Y una ve echo eso, con el siguiente este comando nos abrirá la imagen png en el cual nos mostrara nuestra respectiva flag:
`open flag.png`

### Resultado: picoCTF{beep_boop_im_in_space}

## Referencias: 
https://github.com/colaclanth/sstv
