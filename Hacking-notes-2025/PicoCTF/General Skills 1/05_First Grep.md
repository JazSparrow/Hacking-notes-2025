# First Grep
## Description

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)? This would be really tedious to look through manually, something tells me there is a better way.
##  1 Hints 

grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución 1

Se abre el archivo en el bloc de notas y se busca la cadena el cual inicia "PicoCTF"

```
La respuesta es: picoCTF{grep_is_good_to_find_things_dba08a45}
```

![[Pasted image 20250211220242.png]]

## Solución 2

Se descarga el archivo y se ubica en la carpeta de linux.
Después se ejecuta el comando de cat con un grep y nos muestra el resultado:

```
jazmin@DESKTOP-1CBQJ6D:~/jazmin$ cat file | grep pico
picoCTF{grep_is_good_to_find_things_dba08a45}
jazmin@DESKTOP-1CBQJ6D:~/jazmin$
```

#### Respuesta: picoCTF{grep_is_good_to_find_things_dba08a45}