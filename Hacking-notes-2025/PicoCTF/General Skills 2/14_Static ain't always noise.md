# Static ain't always noise

## Description

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/static)? This [BASH script](https://mercury.picoctf.net/static/ff4e569d6b49b92d090796d4631a2577/ltdis.sh) might help!

## Hints 

(None)

## Solución 1

Descargamos nuestro archivo y lo abrimos en el bloc de notas, después buscamos la palabra clave "Pico" en el cual se encontrara nuestra cadena:

![[Pasted image 20250217113954.png]]

## Solución 2

Se descargan ambos archivos y se utiliza el comando wget, también se dan los permisos para poder ejecutar. se busca vaciar las cadenas a un ejecutable, para solucionarlo se usa cun grep el cual busca en el archivo de strings nuestra flag y finalmente muestra nuestro resultado:

```cmd
jazmin@DESKTOP-1CBQJ6D:~/FIS$ chmod +x static
jazmin@DESKTOP-1CBQJ6D:~/FIS$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
jazmin@DESKTOP-1CBQJ6D:~/FIS$ file ltdis.sh
ltdis.sh: Bourne-Again shell script, ASCII text executable
jazmin@DESKTOP-1CBQJ6D:~/FIS$
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cat ltdis.sh
#!/bin/bash



echo "Attempting disassembly of $1 ..."


#This usage of "objdump" disassembles all (-D) of the first file given by
#invoker, but only prints out the ".text" section (-j .text) (only section
#that matters in almost any compiled program...

objdump -Dj .text $1 > $1.ltdis.x86_64.txt


#Check that $1.ltdis.x86_64.txt is non-empty
#Continue if it is, otherwise print error and eject

if [ -s "$1.ltdis.x86_64.txt" ]
then
        echo "Disassembly successful! Available at: $1.ltdis.x86_64.txt"

        echo "Ripping strings from binary with file offsets..."
        strings -a -t x $1 > $1.ltdis.strings.txt
        echo "Any strings found in $1 have been written to $1.ltdis.strings.txt with file offset"



else
        echo "Disassembly failed!"
        echo "Usage: ltdis.sh <program-file>"
        echo "Bye!"
fi
jazmin@DESKTOP-1CBQJ6D:~/FIS$

jazmin@DESKTOP-1CBQJ6D:~/FIS$ strings static | grep pico
picoCTF{d15a5m_t34s3r_ccb2b43e}
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```

### Resultado: picoCTF{d15a5m_t34s3r_ccb2b43e}