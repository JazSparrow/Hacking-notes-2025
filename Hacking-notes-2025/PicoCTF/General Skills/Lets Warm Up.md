## Descripcion

If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Hints

Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

# Solución 1
### Con python

```python
Jaz_sparrow-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x70)
'p'
```

# Solución 2
### Con cyberchef

En el link se ingresa:
Input: 0x70

Se selecciona para convertir a Hexadecimal:
Recipe: From Hex

Y como resultado nos sale:
Output: p

![[Pasted image 20250210194256.png]]

# Referencias

- https://gchq.github.io/CyberChef/