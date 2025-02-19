# Serpentine

### Description

Find the flag in the Python script
[Download Python script](https://artifacts.picoctf.net/c/35/serpentine.py)

### 1 2 3 4 Hints 

* Try running the script and see what happens
* In the webshell, try examining the script with a text editor like `nano`
* To exit `nano`, press Ctrl and x and follow the on-screen prompts.
* The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

Descargamos nuestro archivo py, después lo abrimos en el visual studio code, vamos a editar nuestro código, nos vamos a la fila del elif choice y ponemos en comentario su print ya que no lo necesitaremos, en seguida agregamos un print_flag para que nos pueda dar nuestra flag:

```python
elif choice == 'b':
#print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')

#Agregamos esta parte al código
print_flag()
```

Una vez realizado este cambio, ejecutamos el programa, nos imprime la serpiente en el menú y nos manda una pregunta de que queremos imprimir, por lo tanto seleccionamos "b", para que nos muestre nuestra respectiva flag:

![[Pasted image 20250218221335.png]]

### Respuesta: picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}
