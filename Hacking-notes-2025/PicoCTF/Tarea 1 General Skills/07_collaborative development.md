# collaborative development

### Description

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/69/challenge.zip)

### 1 2 3 Hints 

* `git branch -a` will let you see available branches
* How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
* Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.


## Solución

Primero descargamos nuestro archivo zip y lo descomprimimos, después lo ubicamos en nuestro linux, entramos a las carpetas y aplicamos un cat, git log y un git show, el cual nos indica que se tiene que imprimir nuestra flag por pasos, nos vamos a las siguientes direcciones para ubicar nuestro archivo de texto en el cual sacaremos el historial de confirmaciones, después sacaremos  3 conformaciones que en el mismo txt nos indica, una vez identificados, hacemos un `git show` y luego se pegara el ID del mensaje de confirmación 3 veces, esto nos va juntando las partes de nuestra flag y al final, juntamos cada print que nos regrese y asi obtenemos nuestra respuesta:


![[Pasted image 20250220224810.png]]

![[Pasted image 20250220224706.png]]

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FIS/
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cd challenge_colla
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla$ cd drop-in
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$ ls
flag.py
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$ cat flag.py
print("Printing the flag...")
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$ git log
commit eb4de2a9826332633c62e44a1a130d9b1a88171a (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    init flag printer
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$ git show
commit eb4de2a9826332633c62e44a1a130d9b1a88171a (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    init flag printer

diff --git a/flag.py b/flag.py
new file mode 100644
index 0000000..77d6cec
--- /dev/null
+++ b/flag.py
@@ -0,0 +1 @@
+print("Printing the flag...")

jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$ git show ad37f59bfdcb1e8052bf7e12e1d89a2adb315cf9
commit ad37f59bfdcb1e8052bf7e12e1d89a2adb315cf9 (feature/part-1)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    add part 1

diff --git a/flag.py b/flag.py
index 77d6cec..6e17fb3 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,2 @@
 print("Printing the flag...")
+print("picoCTF{t3@mw0rk_", end='')
\ No newline at end of file
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$ git show 9792a89fa347abc711f84b7208db18d164d45aca
commit 9792a89fa347abc711f84b7208db18d164d45aca (feature/part-2)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    add part 2

diff --git a/flag.py b/flag.py
index 77d6cec..7ab4e25 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("m@k3s_th3_dr3@m_", end='')
\ No newline at end of file
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$ git show 1308521d0d0b66df1a73e91d5d9e2d74610002e3
commit 1308521d0d0b66df1a73e91d5d9e2d74610002e3 (feature/part-3)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:09:38 2024 +0000

    add part 3

diff --git a/flag.py b/flag.py
index 77d6cec..78ac69c 100644
--- a/flag.py
+++ b/flag.py
@@ -1 +1,3 @@
 print("Printing the flag...")
+
+print("w0rk_e4b79efb}")
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_colla/drop-in$
```
### Resultado: picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_e4b79efb}