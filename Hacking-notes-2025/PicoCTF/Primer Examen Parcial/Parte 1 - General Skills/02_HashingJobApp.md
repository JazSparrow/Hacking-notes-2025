# HashingJobApp

## Description

If you want to hash with the best, beat this test! `nc saturn.picoctf.net 58797`

---

_debug info: [u:754242 e: p: c:243 i:296071]_

## Hints

You can use a commandline tool or web app to hash text
Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución

Iniciamos nuestra instancia y ponemos nuestro link de nc en nuestra terminal de ubuntu o en el webshell del picoCTF, una vez ingresado esto, nos pide sacar el hash MD5 con el texto entre comillas, abrimos otra ventana de nuestra terminal y aplicamos un **echo -n 'a high school bathroom' | md5sum** y con esto nos mostrara una respuesta que es la que ingresaremos y nos dara correcto, escribimos esto con cada texto que nos salga que en total serian 3 veces y al final de poner las respuestas nos dara nuestra respectiva flag.

* NOTA IMPORTANTE: Hay que aplicar los **md5sum** de la manera mas rápida en la segunda terminal, ya que tiene un limite de tiempo aproximado de 20 segundos y si no se completa se tiene que volver a ingresar nuestro link de nc.

## Primera terminal

```
jazmin@DESKTOP-1CBQJ6D:~$ nc saturn.picoctf.net 58797
Please md5 hash the text between quotes, excluding the quotes: 'a high school bathroom'
Answer:
98219c442a477b6dc1756d2a6d49d8df
98219c442a477b6dc1756d2a6d49d8df
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Greenpeace'
Answer:
7628ecff54896cb076074261828e6623
7628ecff54896cb076074261828e6623
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'bad haircut'
Answer:
cdefceb62375fcec3f327834a99e9a58
cdefceb62375fcec3f327834a99e9a58
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}
```

## Segunda terminal

```
jazmin@DESKTOP-1CBQJ6D:~$ echo -n 'a high school bathroom' | md5sum
98219c442a477b6dc1756d2a6d49d8df  -
jazmin@DESKTOP-1CBQJ6D:~$ echo -n 'Greenpeace' | md5sum
7628ecff54896cb076074261828e6623  -
jazmin@DESKTOP-1CBQJ6D:~$ echo -n 'bad haircut' | md5sum
cdefceb62375fcec3f327834a99e9a58  -
jazmin@DESKTOP-1CBQJ6D:~$
```

### Respuesta: picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}