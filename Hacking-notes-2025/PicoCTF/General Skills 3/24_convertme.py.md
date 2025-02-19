# convertme.py

### Description

Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)

### 1 2 3 4 5 6 Hints 

* Look up a decimal to binary number conversion app on the web or use your computer's calculator!
* The `str_xor` function does not need to be reverse engineered for this challenge.
* If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
* To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
* Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
* Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

## Solución

Se descarga nuestro archivo py (python), se abre en visual studio code, hay que considerar que se debe tener la extensión de pyhton para poderlo ejecutar, una vez que nuestro programa corre, nos hace una pregunta el cual es convertir el 58 decimal a binario, una vez que se resuelve la conversión, nos dará como resultado nuestra flag:

![[Pasted image 20250218202146.png]]

### Resultado: picoCTF{4ll_y0ur_b4535_762f748e}

## Referencias:
https://www.prepostseo.com/tool/es/decimal-to-binary-converter
