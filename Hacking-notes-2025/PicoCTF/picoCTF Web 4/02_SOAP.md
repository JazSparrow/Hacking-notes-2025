# SOAP
## Description

The web project was rushed and no security assessment was done. Can you read the /etc/passwd file? [Web Portal](http://saturn.picoctf.net:64224/)
## Hints 1

* XML external entity Injection

## Solución

Entramos al sitio web proporcionado y una vez ahí, damos clic derecho del mouse sobre el botón de PicoCTF y seleccionamos **inspeccionar**, nos dirigimos a **red** y volvemos a dar clic al botón, y veremos los datos que se están mandando, después nos vamos a la parte de **Cabeceras o encabezados** y en otro botón dentro de ahí seleccionamos **Reenviar** y modificaremos el apartado de **Cuerpo**, lo que agregaremos será lo siguiente: 

```
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPEfoo[<!ENTITY example SYSTEM "/etc/passwd">]><data><ID>&example;</ID></data>
```

y nos queda de la siguiente manera:

```
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPEfoo[<!ENTITY example SYSTEM "/etc/passwd">]><data><ID>&example;</ID></data>
```

Damos en **enviar** y nos mostrara nuestra respectiva flag en el apartado de **Respuesta**:                      

![[Pasted image 20250402225512.png]]
### Respuesta: picoCTF{XML_3xtern@l_3nt1t1ty_540f4f1e}

