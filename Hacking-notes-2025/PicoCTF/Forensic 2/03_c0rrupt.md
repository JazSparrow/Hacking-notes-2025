# c0rrupt

#### Description

We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

#### Hints

* Try fixing the file header

## Solución

Primero descargamos nuestro respectivo archivo y lo ubicamos en nuestra carpeta en linux, después abrimos la terminal e ingresamos los siguientes comando a instalar para poder modificar el archivo atreves de hexedit y pngcheck:

`sudo apt install ncurses-hexedit`

`sudo apt install pngcheck`

y utilizaremos el siguiente comando para modificar los números para pasar al archivo a un **PNG**:
`hexeditor flag.png`

`pngcheck flag.png`

Y lo modificamos como en las siguientes imágenes:

![[Pasted image 20250428125234.png]]
![[Pasted image 20250428125554.png]]
![[Pasted image 20250428125750.png]]
![[Pasted image 20250428130312.png]]

y para que nos muestra nuestra respectiva flag utilizaremos el siguiente comando y con esto nos mostrara la respuesta:
`open flag.png`

### Respuesta: picoCTF{c0rrupt10n_1847995}