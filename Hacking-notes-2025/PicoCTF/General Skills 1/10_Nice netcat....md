# Nice netcat...

## Description

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 49039`, but it doesn't speak English...

## 1 2 Hints 

* You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)

* You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)

## Solución

En la terminal webshell se ingresa el siguiente comando para que salgan los números para convertirlos en la página de CyberChef.

```
Jaz_sparrow-picoctf@webshell:~$ nc mercury.picoctf.net 49039
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
51 
100 
56 
52 
101 
100 
99 
56 
125 
10
```

Después en la página de CyberChef se ingresan estos números decimales y los transforma en nuestra cadena, que seria nuestra flag:

![[Pasted image 20250212131236.png]]

#### Por lo tanto nuestro resultado una vez transformado es: picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}

### Referencias
- https://gchq.github.io/CyberChef/