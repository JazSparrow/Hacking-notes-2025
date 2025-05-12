# Tapping

#### Description

Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 21610`.

#### Hints

* What kind of encoding uses dashes and dots?
* The flag is in the format PICOCTF{}

## Solución

En nuestra terminal de ubuntu ingresamos el nc previamente proporcionado, nos dará un mensaje en código morse, entonces utilizaremos el link de **Cyberchef** y en **Recipe** seleccionamos `Morse Code` y pegamos el mensaje y nos mostrará nuestra respectiva flag.
## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ nc jupiter.challenges.picoctf.org 21610
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ...-- ----. ----- ..--- ----- .---- ----. ..... .---- ----. }
```

![[Pasted image 20250512154353.png]]

### Respuesta: PICOCTFM0RS3C0D31SFUN3902019519