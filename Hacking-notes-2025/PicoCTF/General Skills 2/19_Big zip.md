# Big zip

### Description

Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/503/big-zip-files.zip)

### 1 Hints 

Can grep be instructed to look at every file in a directory and its subdirectories?

## Solución

Primeramente descargamos nuestro archivo y abrimos la dirección de enlace con wget y el comando unzip big-zip-files.zip.1 muestra un montón de archivos, pero en este caso, descomprimimos el archivo zip con un unzip, después para poder obtener nuestro resultado se utliza un grep -R picoCTF y con esto nos muestra nuestra respectiva flag:

```
jazmin@DESKTOP-1CBQJ6D:~/FIS$ wget https://artifacts.picoctf.net/c/503/big-zip-files.zip
--2025-02-17 13:26:47--  https://artifacts.picoctf.net/c/503/big-zip-files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3182988 (3.0M) [application/octet-stream]
Saving to: ‘big-zip-files.zip.2’

big-zip-files.zip.2           100%[=================================================>]   3.04M  9.20MB/s    in 0.3s

2025-02-17 13:26:47 (9.20 MB/s) - ‘big-zip-files.zip.2’ saved [3182988/3182988]

jazmin@DESKTOP-1CBQJ6D:~/FIS$ unzip big-zip-files
Archive:  big-zip-files.zip
replace big-zip-files/jpvaawkrpno.txt? [y]es, [n]o, [A]ll, [N]one, [r]ename: yes
 extracting: big-zip-files/jpvaawkrpno.txt
jazmin@DESKTOP-1CBQJ6D:~/FIS$ grep -R picoCTF
flag:picoCTF{s4n1ty_v3r1f13d_4a2b35fd}
Binary file files.zip matches
Binary file Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet matches
Binary file static matches
files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt:picoCTF{f1nd_15_f457_ab443fd1}
Binary file files.zip.1 matches
Binary file strings matches
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
file:picoCTF{grep_is_good_to_find_things_dba08a45}
Binary file warm matches
jazmin@DESKTOP-1CBQJ6D:~/FIS$
```

### Resultado: picoCTF{gr3p_15_m4g1c_ef8790dc}