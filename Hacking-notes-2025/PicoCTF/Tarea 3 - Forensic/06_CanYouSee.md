# CanYouSee

#### Description

How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/5/unknown.zip).

#### Hints

* How can you view the information about the picture?
* If something isn't in the expected form, maybe it deserves attention?

## Solución

Primeramente descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Enseguida descomprimimos el archivo que es un zip con el siguiente comando:

`unzip unknown.zip`

Después ingresamos el siguiente comando para que nos muestre los tipos de archivo que vienen dentro: 

`exiftool ukn_reality.jpg`

En la parte de `Attribution URL` y copiamos el cifrado y lo ingresamos en un link de cyberchef y lo pasamos a `from base64` para transformarlo a nuestra respectiva flag.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ unzip unknown.zip
Archive:  unknown.zip
   inflating: ukn_reality.jpg?
jazmin@DESKTOP-1CBQJ6D:~/FSI$ exiftool ukn_reality.jpg
ExifTool Version Number         : 11.88
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.2 MB
File Modification Date/Time     : 2024:02:15 16:40:17-06:00
File Access Date/Time           : 2025:05:10 14:31:18-06:00
File Inode Change Date/Time     : 2025:05:10 14:29:02-06:00
File Permissions                : rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fNGRhYmRkY2J9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
jazmin@DESKTOP-1CBQJ6D:~/FSI$
```

![[Pasted image 20250510211618.png]]
### Respuesta: picoCTF{ME74D47A_HIDD3N_4dabddcb}

### Referencias

- https://gchq.github.io/CyberChef/