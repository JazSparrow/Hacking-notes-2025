# Easy1

#### Description

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

#### Hints

* Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{HELLO}' as the flag.
* Please use all caps for the message.

## Solución

En nuestro link de cyberchef en **Recipe** seleccionamos `Vigenere Decode` e ingresamos el encriptado `UFJKXQZQUNB` y en la **Key** ponemos el `SOLVECRYPTO` que se nos proporciona en la descripción y nos mostrara nuestra respectiva flag, solo escribimos picoCTF y los {}.


![[Pasted image 20250512145409.png]]

### Respuesta: picoCTF{CRYPTOISFUN}