# binary search

### Description

Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/4/challenge.zip)

Additional details will be available after launching your challenge instance.

`ssh -p 52060 ctf-player@atlas.picoctf.net`Using the password `83dcefb7`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!


### 1 2 3 Hints 

* Have you ever played hot or cold? Binary search is a bit like that.
* You have a very limited number of guesses. Try larger jumps between numbers!
* The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?

## Solución

Ingresamos nuestra dirección ssh proporcionada, ponemos la contraseña y una vez dado los permisos, se inicia el programa, el propósito es buscar un numero entre 1 y 1000 el cual se escoge aleatoriamente, comenzamos ingresando un 500, ya que es un intermedio y nos indicara si es mayor o menor, para sacar las respuestas mas precisamente se utiliza una regla de tres, en este caso lo primero que nos dice es que el numero es mayor que 500, entonces realizamos la siguiente operación:
501+1000/2=751, usamos este método hasta obtener un aproximado hasta que nos salga nuestro resultado y con esto nos dará la flag.
###### Nota importante: considerar que el programa solo deja ejecutar 10 intentos.

```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ ssh -p 52060 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:52060 ([18.217.83.136]:52060)' can't be established.
ECDSA key fingerprint is SHA256:ordTMCwK3qpNza5KnIvhhv3zuT2jVOfUn+VlRwYK23s.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:52060,[18.217.83.136]:52060' (ECDSA) to the list of known hosts.
ctf-player@atlas.picoctf.net's password:
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 751
Higher! Try again.
Enter your guess: 876
Higher! Try again.
Enter your guess: 939
Lower! Try again.
Enter your guess: 908
Lower! Try again.
Enter your guess: 892
Lower! Try again.
Enter your guess: 884
Lower! Try again.
Enter your guess: 880
Lower! Try again.
Enter your guess: 878
Higher! Try again.
Enter your guess: 879
Congratulations! You guessed the correct number: 879
Here's your flag: picoCTF{g00d_gu355_ee8225d0}
Connection to atlas.picoctf.net closed.
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```

### Resultado: picoCTF{g00d_gu355_ee8225d0}