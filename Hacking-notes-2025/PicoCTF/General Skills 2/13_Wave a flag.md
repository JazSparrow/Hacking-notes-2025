# Wave a flag

### Description

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm) has extraordinarily helpful information...

### 1 2 3 4 5 Hints 

* This program will only work in the webshell or another Linux computer.
* To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/a14be2648c73e3cda5fc8490a2f476af/warm`
* Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
* -h and --help are the most common arguments to give to programs to get more information from them!
* Not every program implements help features like -h and --help.

## Solución 1

Se descarga el archivo y se abre en un bloc de notas, enseguida buscamos la palabra en clave "pico" para que nos aparezca nuestra flag:

![[Pasted image 20250216192932.png]]

## Solución 2

Se descarga nuestro archivo en linux y se abre la terminar para ingresar los comandos especificados y con esto, nos muestra nuestra flag:

![[Pasted image 20250216193109.png]]

### Resultado: picoCTF{b1scu1ts_4nd_gr4vy_755f3544}