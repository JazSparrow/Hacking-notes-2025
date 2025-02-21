# time machine

### Description

What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/161/challenge.zip)

### 1 2 3 Hints 

* The `cat` command will let you read a file, but that won't help you here!
* Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
* When committing a file with git, a message can (and should) be included.


## Solución
 Descargamos nuestro archivo zip y lo extraemos, una vez echo esto, vamos a nuestra terminal de linux y entramos en las carpetas del zip, después aplicamos un git log el cual nos muestra un registro del historial y en el cual se confirma nuestra flag, de igual manera también se puede usar un got show el cual nos va dar mas detalles y nuestro resultado:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FIS/
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cd challenge_time
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_time$ cd drop-in
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_time/drop-in$ ls
message.txt
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_time/drop-in$ git log
commit 10228f3d6437701ef5aaac04213757031f30ebec (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:24 2024 +0000

    picoCTF{t1m3m@ch1n3_8defe16a}
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_time/drop-in$ git show
commit 10228f3d6437701ef5aaac04213757031f30ebec (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:24 2024 +0000

    picoCTF{t1m3m@ch1n3_8defe16a}

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..4324621
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+This is what I was working on, but I'd need to look at my commit history to know why...
\ No newline at end of file
jazmin@DESKTOP-1CBQJ6D:~/FIS/challenge_time/drop-in$
```

### Resultado: picoCTF{t1m3m@ch1n3_8defe16a}
