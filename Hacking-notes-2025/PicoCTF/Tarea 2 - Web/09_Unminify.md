# Unminify

## Description

I don't like scrolling down to read the code of my website, so I've squished it. As a bonus, my pages load faster! Browse [here](http://titan.picoctf.net:58088/), and find the flag!

---
## Hints 1 2 3

* Try CTRL+U / ⌘+U in your browser to view the page source. You can also add 'view-source:' before the URL, or try `curl <URL>` in your shell.
* Minification reduces the size of code, but does not change its functionality.
* What tools do developers use when working on a website? Many text editors and browsers include formatting.

## Solución

Iniciamos nuestra instancia y entramos al sitio web proporcionado, una vez ahí, en la imagen que se observa damos clic derecho con el mouse y seleccionamos **Inspeccionar**, una vez dentro del código vamos seleccionando las flechas hasta encontrar nuestra respectiva flag que estaba escondida en la página.
![[Pasted image 20250401182228.png]]
### Respuesta: picoCTF{pr3tty_c0d3_622b2c88}