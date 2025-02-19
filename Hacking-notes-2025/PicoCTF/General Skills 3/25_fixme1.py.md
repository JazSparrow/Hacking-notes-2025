# fixme1.py

### Description

Fix the syntax error in this Python script to print the flag.
[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)

### 1 2 3 4 Hints 

* Indentation is very meaningful in Python
* To view the file in the webshell, do: `$ nano fixme1.py`
* To exit `nano`, press Ctrl and x and follow the on-screen prompts.
* The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

Primero se descarga nuestro archivo py, una vez echo eso, se debe encontrar el error en el código, primeramente abrimos el archivo en el visual studio code, el código nos indica que hay un error, en la fila 20 se nos indica que hay que borrar un espacio sobrante, una vez echo esto, ejecutamos nuestro programa y nos muestra nuestra flag: 

![[Pasted image 20250218203719.png]]

### Resultado: picoCTF{1nd3nt1ty_cr1515_182342f7}