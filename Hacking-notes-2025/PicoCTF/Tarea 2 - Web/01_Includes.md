# Includes

## Description

Can you get the flag?Go to this [website](http://saturn.picoctf.net:65471/) and see what you can discover.
This challenge launches an instance on demand.  

---
## Hints 1

* Is there more code than what the inspector initially shows?

## Solución

Iniciamos la instancia y entramos al sitio web que nos indica, y nos dirige a la siguiente ventana, una vez en la página damos clic derecho en el botón y seleccionamos **"Ver código fuente de la página"**.

![[Pasted image 20250401170952.png]]

Nos manda a esta parte del código y enseguida notamos que hay dos links directos que son "[style.css](http://saturn.picoctf.net:65471/style.css)" y "[script.js](http://saturn.picoctf.net:65471/script.js)" y damos clic en ellos, nos manda a otra página en la cuál nos muestra dos partes de la bandera que hay que juntar y queda de la siguiente manera, con esto completamos nuestra flag.
##### Primera parte:
```
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */
```
##### Segunda parte:
```
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_df589022}
```

### Respuesta: picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}