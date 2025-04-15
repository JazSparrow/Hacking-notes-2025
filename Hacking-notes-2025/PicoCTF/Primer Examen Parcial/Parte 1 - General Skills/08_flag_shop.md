# flag_shop
## Description

There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/253c4651d852ac6342752ff222cf2a83/store.c). Connect with `nc jupiter.challenges.picoctf.org 9745`.

## Hints

* Two's compliment can do some weird things when numbers get really big!

## Solución

Abrimos nuestra terminal de ubuntu y descargamos el archivo de pyhton llamado: **store.py** y lo ubicamos en nuestra carpeta de linux, después ingresamos nuestro link de nc.
	En seguida ingresamos los números 1 y 2, dependiendo de lo que nos pregunte y el dinero que se pida, por ejemplo si pide ingresar ceros después del 1, como por ejemplo `100000000000000000` y nos muestra nuestra respectiva flag.

```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ nc jupiter.challenges.picoctf.org 9745
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 1100


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
1

The final cost is: 900

Your current balance after transaction: 200

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1

Not enough funds for transaction


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one10000000000000000
jazmin@DESKTOP-1CBQJ6D:~/FIS$ nc jupiter.challenges.picoctf.org 9745
Welcome to the flag exchange
We sell flags

3. Check Account Balance

4. Buy Flags

5. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
100000000000000000

The final cost is: -651689984

Your current balance after transaction: 651691084

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_65d67a74}
Welcome to the flag exchange
We sell flags

3. Check Account Balance

4. Buy Flags

5. Exit

 Enter a menu selection
```

### Respuesta: picoCTF{m0n3y_bag5_65d67a74}