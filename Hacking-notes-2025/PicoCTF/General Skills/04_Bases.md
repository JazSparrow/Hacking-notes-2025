# Bases

## Description

What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## 1 Hints

Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución 1
#### Con cyberchef

Ingresamos en el link:
Input: bDNhcm5fdGgzX3IwcDM1

Se selecciona Base64 para convertir la frase:
Recipe: From Base64

Y el resultado es:
Output: l3arn_th3_r0p35

![[Pasted image 20250211214738.png]]
## Solución 2

```
Jaz_sparrow-picoctf@webshell:~$ echo bDNhcm5fdGgzX3IwcDM1 | base64 -d
l3arn_th3_r0p35Jaz_sparrow-picoctf@webshell:~$
```

#### Respuesta: PicoCTF{l3arn_th3_r0p35}

### Referencias
- https://gchq.github.io/CyberChef/