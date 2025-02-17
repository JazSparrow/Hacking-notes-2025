# 2Warm

### Description

Can you convert the number 42 (base 10) to binary (base 2)?
### 1  Hints 

Submit your answer in our competition's flag format. For example, if your answer was '11111', you would submit 'picoCTF{11111}' as the flag.

## Solución 1
#### Con python

```python
Jaz_sparrow-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
>>> bin(42)[2:]
'101010'
>>> 
```

## Solución 2
#### Con cyberchef

En el link se ingresa:
Input: 42

Se selecciona de decimal a binario para convertirlo:
Recipe: From Decimal To Binary

Y nuestro resultado es:
Output: 101010
![[Pasted image 20250212121711.png]]
#### Respuesta: picoCTF{101010}

### Referencias

- https://gchq.github.io/CyberChef/