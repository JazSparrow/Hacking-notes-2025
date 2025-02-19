# PW Crack 1

### Description

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

### 1 2 3 Hints 

* To view the file in the webshell, do: `$ nano level1.py`
* To exit `nano`, press Ctrl and x and follow the on-screen prompts.
* The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

Primero se descarga nuestro archivo py y un enc, los ubicamos en una misma carpeta llamada level1, después abrimos el py en el visual studio code, en el mismo código nos indica cual es nuestra contraseña, una vez ubicado eso, ejecutamos nuestro programa, ingresamos la contraseña encontrada y nos muestra nuestra flag: 

![[Pasted image 20250218205920.png]]

### Resultado: picoCTF{545h_r1ng1ng_56891419}