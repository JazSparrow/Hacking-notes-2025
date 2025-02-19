# PW Crack 3

### Description

Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/18/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

### 1 2 3 Hints 

* To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
* To exit `bvi` type `:q` and press enter.
* The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

Descargamos nuestro archivo py, un enc y un bin, los ubicamos en una misma carpeta llamada level3, después abrimos el py en el visual studio code, una vez ahi editamos el código, vienen comentarios de cuales fueron las partes editadas y lo que se agrego y quito del mismo:

```python
flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):

    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

#Se agrega una lista en la cual nos dara alguna de las contraseñas para nuestra flag, esta parte se coloca entre la primera y la segunda definición
pos_pw_list = ["8799", "d3ab", "1ea2", "acaf", "2295", "a9de", "6f3d"]

def level_3_pw_check():

    #Esto se puso en un comentario ya que no lo necesitaremos
    #user_pw = input("Please enter correct password for flag: ")

    #Agregamos un for y una lista
    for user_pw in pos_pw_list:
        user_pw_hash = hash_pw(user_pw)

        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)

            #Se agrego la variable user_pw para imprimirla
            print(user_pw)
            print(decryption)
            return
        print("That password is incorrect")

level_3_pw_check()

```

Una vez hechos los cambios en el código, automáticamente nos dará una de las contraseñas y nos da nuestra respectiva flag:

![[Pasted image 20250218215247.png]]

### Resultado: picoCTF{m45h_fl1ng1ng_6f98a49f}