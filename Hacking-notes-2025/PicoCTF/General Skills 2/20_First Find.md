# First Find

### Description

Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/501/files.zip)

### Hints 

(None)

## Solución

Descargamos nuestro archivo y abrimos la dirección de enlace con wget , se va a realizamos un unzip al zip, enseguida se busca el archivo usando el comando find y por ultimo se realiza un cat al archivo previamente encontrado y con esto nos muestra nuestra flag:

```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ wget https://artifacts.picoctf.net/c/501/files.zip
--2025-02-17 13:21:41--  https://artifacts.picoctf.net/c/501/files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3995553 (3.8M) [application/octet-stream]
Saving to: ‘files.zip.1’

files.zip.1                   100%[=================================================>]   3.81M  6.81MB/s    in 0.6s

2025-02-17 13:21:42 (6.81 MB/s) - ‘files.zip.1’ saved [3995553/3995553]

jazmin@DESKTOP-1CBQJ6D:~/FIS$ ls
Addadshashanammu                      enc_flag                   flag                      strings
Addadshashanammu.zip                  enc_flag:Zone.Identifier   flag:Zone.Identifier      strings:Zone.Identifier
Addadshashanammu.zip.1                file                       ltdis.sh                  warm
Addadshashanammu.zip:Zone.Identifier  file:Zone.Identifier       ltdis.sh.save             warm:Zone.Identifier
big-zip-files                         files.zip                  ltdis.sh:Zone.Identifier
big-zip-files.zip                     files.zip.1                static
big-zip-files.zip.1                   files.zip:Zone.Identifier  static:Zone.Identifier
jazmin@DESKTOP-1CBQJ6D:~/FIS$ unzip files.zip
Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
  inflating: files/satisfactory_books/more_books/37121.txt.utf-8
  inflating: files/satisfactory_books/23765.txt.utf-8
  inflating: files/satisfactory_books/16021.txt.utf-8
  inflating: files/13771.txt.utf-8
   creating: files/adequate_books/
   creating: files/adequate_books/more_books/
   creating: files/adequate_books/more_books/.secret/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
  inflating: files/adequate_books/more_books/1023.txt.utf-8
  inflating: files/adequate_books/46804-0.txt
  inflating: files/adequate_books/44578.txt.utf-8
   creating: files/acceptable_books/
   creating: files/acceptable_books/more_books/
  inflating: files/acceptable_books/more_books/40723.txt.utf-8
  inflating: files/acceptable_books/17880.txt.utf-8
  inflating: files/acceptable_books/17879.txt.utf-8
  inflating: files/14789.txt.utf-8
jazmin@DESKTOP-1CBQJ6D:~/FIS$
jazmin@DESKTOP-1CBQJ6D:~/FIS$ find . -name uber-secret.txt
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
picoCTF{f1nd_15_f457_ab443fd1}
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```

### Respuesta: picoCTF{f1nd_15_f457_ab443fd1}