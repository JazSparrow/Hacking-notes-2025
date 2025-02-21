# binhexa

### Description

How well can you perfom basic binary operations?

Additional details will be available after launching your challenge instance.

Start searching for the flag here `nc titan.picoctf.net 51915`

### Hints 

(None)

## Solución

En nuestra terminal de linux, copiamos el link de nc y con esto inicia el reto de las operaciones en binario:

##### Operación 1: '|'
* La operación `|` **(OR bit a bit)** compara cada bit de los números binarios y devuelve `1` si al menos uno de los bits es `1`; de lo contrario, devuelve `0`.
```
| 00110001
| 10000101 
----------
  10110101 
```

##### Operación 2: '+'

* La operación `+` indica una **suma** de los números binarios.
```
  00110001  (49 en decimal)
+ 10000101  (133 en decimal)
---------------
49 + 133 = 182
182 ​= 10110110
```

##### Operación 3: 'x'
* La operación `*` se refiere a la **multiplicación** de los números binarios.

```
00110001₂ = 49₁₀
10000101₂ = 133₁₀
------------------
49 × 133 = 6517
6517 ​= 1100101110101
```

##### Operación 4: '&'
* La operación `&` **(AND bit a bit)** compara cada bit de los números binarios y devuelve `1` solo si ambos bits son `1`; de lo contrario, devuelve `0`.

```
  00110001  
& 10000101  
------------
  00000001  
```

##### Operación 5: '>>'
* La operación `>>` mueve los bits del número hacia la derecha, rellenando con ceros a la izquierda.
```
Número binario original (Binary Number 2):
`10000101`

Desplazamiento a la derecha por 1 bit:
`01000010`
```

##### Operación 6: '<<'
* La operación `<<` mueve los bits del número hacia la izquierda, rellenando con ceros a la derecha.
```
Número binario original (Binary Number 1):
`00110001`

Desplazamiento a la izquierda por 1 bit:
`01100010`
```

##### Binario a Hexadecimal:
* Para convertir el resultado de la última operación (**01100010** en binario) a hexadecimal:

1. Agrupamos los bits en grupos de 4, comenzando desde la derecha:

`0110 0010`

2. Convertimos cada grupo de 4 bits a su valor hexadecimal:

- **0110** = **6**
- **0010** = **2**

Por lo tanto, nuestro resultado en **hexadecimal** es: **62**.

Una vez echo esto nos dará nuestra respectiva flag:

### Terminal en linux:
```
jazmin@DESKTOP-1CBQJ6D:~$ nc titan.picoctf.net 51915

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 00110001
Binary Number 2: 10000101


Question 1/6:
Operation 1: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10110101
Correct!

Question 2/6:
Operation 2: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10110110
Correct!

Question 3/6:
Operation 3: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1100101110101
Correct!

Question 4/6:
Operation 4: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00000001
Correct!

Question 5/6:
Operation 5: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 01000010
Correct!

Question 6/6:
Operation 6: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 01100010
Correct!

Enter the results of the last operation in hexadecimal: 62

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_aeaf4b09}
```

### Resultado: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_aeaf4b09}

## Referencias:
* https://es.planetcalc.com/911/
* https://masterplc.com/calculadora/convertir-binario-a-decimal/
* Calculadora de Windows en modo Programador.