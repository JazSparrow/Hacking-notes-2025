# strings it

### Description

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

### Hints 

[strings](https://linux.die.net/man/1/strings)

## Solución 1

Descargar el archivo y abrirlo en el bloc de notas, enseguida buscar la palabra clave "Pico" en el cual se encontrara nuestra cadena:

![[Pasted image 20250215204857.png]]

## Solución 2

Se usa el comando para sacar las cadenas pero como salen muchas y el propósito es reducirlas y encontrar la que nos interesa, entonces se ingresa un grep pico y nos muestra nuestra flag:

```cmd
jazmin@DESKTOP-1CBQJ6D:~/FIS$ strings -n 10 strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```
### Resultado: picoCTF{5tRIng5_1T_7f766a23}