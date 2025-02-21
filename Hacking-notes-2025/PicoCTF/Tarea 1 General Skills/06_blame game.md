# blame game

### Description

Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/74/challenge.zip)

### 1 2 3 Hints 

* In collaborative projects, many users can make many changes. How can you see the changes within one file?
* Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
* You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.

## Solución

Para realizar este ejercicio, primero se descargo nuestro archivo zip y lo descomprimimos, una vez realizado esto, seguimos las siguientes direcciones de carpeta en la cual encontraremos un archivo de texto y lo abrimos en el bloc de notas, una vez echo esto, buscamos la palabra en clave "pico" y nos aparecerá nuestra respectiva flag:

![[Pasted image 20250220222023.png]]

![[Pasted image 20250220222057.png]]

### Resultado: picoCTF{@sk_th3_1nt3rn_ea346835}