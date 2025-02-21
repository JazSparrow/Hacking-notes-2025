# Commitment Issues

### Description

I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/77/challenge.zip)

### 1 2 3 Hints 

* Version control can help you recover files if you change or lose them!
* Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)
* You can 'checkout' commits to see the files inside them

## Solución

Descargamos nuestro archivo zip y lo extraemos, una vez echo esto, vamos a nuestra terminal de linux y entramos en las carpetas del zip hasta encontrar un archivo de texto, cuando observamos lo que hay dentro, aplicamos un git show para que nos muestre el mensaje secreto y mas detalles y de ahí nos muestra nuestra flag:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FIS/
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cd challenge
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge$ cd drop-in
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge/drop-in$ ls
message.txt
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge/drop-in$ cat message.txt
TOP SECRET
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge/drop-in$ git show
commit e1237df82d2e69f62dd53279abc1c8aeb66f6d64 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    remove sensitive info

diff --git a/message.txt b/message.txt
index 96f7309..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_30e86d36}
+TOP SECRET
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge/drop-in$
```

### Resultado: picoCTF{s@n1t1z3_30e86d36}