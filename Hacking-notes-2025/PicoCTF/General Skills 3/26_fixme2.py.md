# fixme2.py

### Description

Fix the syntax error in the Python script to print the flag.
[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py)

### 1 2 3 4 Hints 

* Are equality and assignment the same symbol?
* To view the file in the webshell, do: `$ nano fixme2.py`
* To exit `nano`, press Ctrl and x and follow the on-screen prompts.
* The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

Primero se descarga nuestro archivo py, una vez echo eso, se debe encontrar el error en el código, primeramente abrimos el archivo en el visual studio code, el código nos indica que hay un error, en la fila 22 se nos indica que hay que agregar un "=" ya que estaba incompleto, una vez echo esto, ejecutamos nuestro programa y nos muestra nuestra flag: 

![[Pasted image 20250218204913.png]]

### Resultado: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}