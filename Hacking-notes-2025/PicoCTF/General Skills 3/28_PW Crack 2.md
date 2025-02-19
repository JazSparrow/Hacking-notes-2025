# PW Crack 2

### Description

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

### 1 2 Hints 

* Does that encoding look familiar?
* The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución 

Descargamos nuestro archivo py y un enc, los ubicamos en una misma carpeta llamada level2, después abrimos el py en el visual studio code, una vez abierto copiamos la cadena del user_pw y le agregamos un print, después del flag_enc y antes de la def, de la siguiente manera:

```python
print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))
```

Una vez escrito el print correspondiente, ejecutamos el programa y nos muestra nuestra nuestra contraseña para la flag, la ingresamos en la terminal y nos muestra nuestro resultado: 

![[Pasted image 20250218211208.png]]

### Resultado: picoCTF{tr45h_51ng1ng_502ec42e}