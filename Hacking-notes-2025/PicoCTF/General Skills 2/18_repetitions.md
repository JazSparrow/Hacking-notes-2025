# repetitions

### Description

Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/472/enc_flag).

### 1 Hints

* Multiple decoding is always good.

## Solución

 Se descarga el archivo y se abre en un bloc de notas, una vez abierto nos damos cuenta de que es una decodificación en base64 ya que es bastante largo, para resolverlo buscamos una pagina para decodificar el texto, después de copiar y pegar varias veces el texto en la pagina (6 veces), finalmente nos sale nuestra flag:
 
![[Pasted image 20250216200342.png]]

### Resultado: picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_73494190}

## Referencias
https://www.base64decode.org/es/