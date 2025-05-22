# Mind your Ps and Qs

### Description

In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values)

### Hints

* Bits are expensive, I used only a little bit over 100 to save money

## Solución

Primero descargamos el archivo que nos aparece en nuestra descripción con el wget.
Enseguida aplicamos un `cat` al archivo y nos mostrara los datos que necesitaremos para el código en python:

* `cat values`

## Terminal de ejemplo

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FSI
jazmin@DESKTOP-1CBQJ6D:~/FSI$ mkdir mindpsqs
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd mindpsqs
jazmin@DESKTOP-1CBQJ6D:~/FSI/mindpsqs$ wget https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values
--2025-05-21 12:36:26--  https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: ‘values’

values                        100%[=================================================>]     206  --.-KB/s    in 0s

2025-05-21 12:36:27 (18.0 MB/s) - ‘values’ saved [206/206]
jazmin@DESKTOP-1CBQJ6D:~/FSI/mindpsqs$ cat values
Decrypt my super sick RSA:
c: 843044897663847841476319711639772861390329326681532977209935413827620909782846667
n: 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
e: 65537
jazmin@DESKTOP-1CBQJ6D:~/FSI/mindpsqs$
```

En la terminal, abrimos el python3 para ingresar los datos que se nos proporcionaron y nos basaremos en el formulario que anteriormente vimos y nos quedaría de la siguiente manera:

Y para que nos muestra nuestra flag aplicamos la siguiente formula:

* `bytes.fromhex(hex(m)[2:])`
## Terminal en python3

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ python3
Python 3.8.10 (default, Mar 18 2025, 20:04:55)
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c = 843044897663847841476319711639772861390329326681532977209935413827620909782846667
>>> n = 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> e = 65537
>>> p = 2159947535959146091116171018558446546179
>>> q = 658558036833541874645521278345168572231473
>>> p * q
1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> tn = (p-1) * (q-1)
>>> tn
1422450808944701344261903748621562998783582944057933890341955406374353056752914016
>>> d = pow(e, -1, tn)
>>> m = pow(c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639555294957886055592061
>>> bytes.fromhex(hex(m)[2:])
b'picoCTF{sma11_N_n0_g0od_00264570}'
>>>
```

### Respuesta: picoCTF{sma11_N_n0_g0od_00264570}

## Referencias
* https://factordb.com