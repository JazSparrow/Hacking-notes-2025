# Local Authority

## Description

Can you get the flag? Go to this [website](http://saturn.picoctf.net:58866/) and see what you can discover.

---
## Hints 1

* How is the password checked on this website?

## Solución

Iniciamos nuestra instancia y entramos al sitio web proporcionado, una vez ahí, damos clic derecho con el mouse y seleccionamos **"Ver código fuente de la página"**, esto nos dirige a otra pestaña y ahí nos muestra el código, pero no se encuentra nuestra flag, por lo tanto, regresamos a la página y damos clic derecho y seleccionamos **Inspeccionar** y dentro de ahí damos clic en **Red**, después de hacer esto, tratamos de acceder con un **usuario y contraseña**, en este caso, **admin y admin**, y ons muestra unos datos en el **login.php**, enseguida vamos al **código fuente de la página** del login.php, entonces nos muestra una página de código, y nos dirigimos al "[secure.js](view-source:http://saturn.picoctf.net:58866/secure.js)" y nos muestra el siguiente texto, en el que contiene la contraseña que utilizaremos para entrar con el usuario de admin:

```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

Una vez copiado la contraseña, la ingresamos junto con el admin y con esto nos muestra nuestra respectiva flag:

![[Pasted image 20250401175925.png]]

![[Pasted image 20250401180002.png]]

### Respuesta: picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}