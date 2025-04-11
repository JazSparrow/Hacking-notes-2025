# Cookie Monster Secret Recipe
## Description

Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe? You can access the Cookie Monster [here](http://verbal-sleep.picoctf.net:64848/) and good luck

## Hints 1 2 3

* Sometimes, the most important information is hidden in plain sight. Have you checked all parts of the webpage?
* Cookies aren't just for eating - they're also used in web technologies!
* Web browsers often have tools that can help you inspect various aspects of a webpage, including things you can't see directly.

## Solución

Primero entramos al link proporcionado, después ingresamos cualquier usuario y contraseña, una vez echo vamos al **Cookie-Editor** y copiamos su **value**.
![[Pasted image 20250408151746.png]]

Después vamos a la página de **cyberchef** y seleccionamos **From base64** y lo pegamos, con esto nos da nuestra flag:

![[Pasted image 20250408152823.png]]

### Respuesta: picoCTF{c00k1e_m0nster_l0ves_c00kies_771D5EB0}

## Referiencias:

https://gchq.github.io/CyberChef/
