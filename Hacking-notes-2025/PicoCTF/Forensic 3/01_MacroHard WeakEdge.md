# MacroHard WeakEdge

#### Description

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c00c449c3b08daaccacca6f9d5c55d49/Forensics is fun.pptm)

#### Hints

* (None)

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta de linux, enseguida nos dirigimos a la terminal y entramos a las siguientes carpetas:
`cd macro`
`cd ppt`
`cd slideMasters`
 
Y enseguida aplicamos los siguientes comandos para que nos convierta nuestro cifrado y nos muestre nuestra respectiva flag:

`cat hidden`
`cat hidden | sed 's/ //'`
`cat hidden | sed 's/ //g'`
`cat hidden | sed 's/ //g' | base64 -d`

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FSI/
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd macro
jazmin@DESKTOP-1CBQJ6D:~/FSI/macro$ ls
'[Content_Types].xml'   _rels   docProps   ppt
jazmin@DESKTOP-1CBQJ6D:~/FSI/macro$ cd ppt
jazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt$ ls
_rels          presentation.xml  slideMasters  tableStyles.xml  vbaProject.bin
presProps.xml  slideLayouts      slides        theme            viewProps.xml
jazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt$ cd slideMasters
jazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt/slideMasters$ cat hidden
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Qjazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt/slideMasters$ cat hidden | sed 's/ //'
Zm x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Qjazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt/slideMasters$ cat hidden | sed 's/ //g'
ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQjazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt/slideMasters$
jazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt/slideMasters$ cat hidden | sed 's/ //g' | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input
jazmin@DESKTOP-1CBQJ6D:~/FSI/macro/ppt/slideMasters$
```

### Respuesta: picoCTF{D1d_u_kn0w_ppts_r_z1p5}