# runme.py

## Description

Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.
[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

## 1 2 3 4 Hints 

* If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
* To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
* Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
* Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 runme.py` You should have the flag now!

## Solución 1

Para solucionarlo se descarga nuestro archivo python, después entramos a nuestra terminal de linux, visualizamos el contenido de nuestra carpeta y nos aseguramos de que se encuentre nuestro py, después corremos nuestro archivo con el comando python3 y nos muestra nuestra flag:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FIS/
jazmin@DESKTOP-1CBQJ6D:~/FIS$ ls
Addadshashanammu                      enc_flag                   flag                      static:Zone.Identifier
Addadshashanammu.zip                  enc_flag:Zone.Identifier   flag:Zone.Identifier      strings
Addadshashanammu.zip.1                file                       ltdis.sh                  strings:Zone.Identifier
Addadshashanammu.zip:Zone.Identifier  file:Zone.Identifier       ltdis.sh.save             warm
big-zip-files                         files                      ltdis.sh:Zone.Identifier  warm:Zone.Identifier
big-zip-files.zip                     files.zip                  runme.py
big-zip-files.zip.1                   files.zip.1                runme.py:Zone.Identifier
big-zip-files.zip.2                   files.zip:Zone.Identifier  static
jazmin@DESKTOP-1CBQJ6D:~/FIS$ python3 runme.py
picoCTF{run_s4n1ty_run}
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```

## Solución 2

Una vez descargado nuestro archivo py, lo abrimos en el visual studio y el contenido del archivo es la respectiva flag:

![[Pasted image 20250218200210.png]]

### Resultado: picoCTF{run_s4n1ty_run}