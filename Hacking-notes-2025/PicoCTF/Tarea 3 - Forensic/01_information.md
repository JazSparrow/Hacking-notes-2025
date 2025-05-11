# information

#### Description

Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg)

#### Hints

* Look at the details of the file
* Make sure to submit the flag as picoCTF{XXXXX}

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux.

Ingresamos a nuestra terminal de ubuntu e ingresamos los siguientes comandos:

`exiftool cat.jpg`
`exiftool cat.jpg | grep License`
`exiftool cat.jpg | grep License | sed -e 's/.*: //'`
`exiftool cat.jpg | grep License | sed -e 's/.*: //' | base64 -d`

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ exiftool cat.jpg
ExifTool Version Number         : 11.88
File Name                       : cat.jpg
Directory                       : .
File Size                       : 858 kB
File Modification Date/Time     : 2025:05:10 21:16:42-06:00
File Access Date/Time           : 2025:05:10 21:17:24-06:00
File Inode Change Date/Time     : 2025:05:10 21:17:24-06:00
File Permissions                : rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
jazmin@DESKTOP-1CBQJ6D:~/FSI$ exiftool cat.jpg | grep License
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
jazmin@DESKTOP-1CBQJ6D:~/FSI$ exiftool cat.jpg | grep License | sed -e 's/.*: //'
cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
jazmin@DESKTOP-1CBQJ6D:~/FSI$ exiftool cat.jpg | grep License | sed -e 's/.*: //' | base64 -d
picoCTF{the_m3tadata_1s_modified}jazmin@DESKTOP-1CBQJ6D:~/FSI$
```

### Respuesta: picoCTF{the_m3tadata_1s_modified}

