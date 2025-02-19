# Codebook

### Description

Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

### 1 2 Hints 

* On the webshell, use `ls` to see if both files are in the directory you are in
* The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

Primeramente abrimos la dirección de enlace del code.py y del codebook.txt con wget, después observamos que hay en las carpetas con ls, enseguida se ejecuta nuestro archivo py con python y con esto nos da nuestra flag:

```
Jaz_sparrow-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2025-02-19 02:06:20--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.92, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                         100%[======================================================================================================>]   1.25K  --.-KB/s    in 0s      

2025-02-19 02:06:21 (48.5 MB/s) - 'code.py' saved [1278/1278]

Jaz_sparrow-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2025-02-19 02:06:45--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                    100%[======================================================================================================>]      27  --.-KB/s    in 0s      

2025-02-19 02:06:45 (34.7 MB/s) - 'codebook.txt' saved [27/27]

Jaz_sparrow-picoctf@webshell:~$ ls
README.txt  code.py  codebook.txt  salida
Jaz_sparrow-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
Jaz_sparrow-picoctf@webshell:~$
```

### Resultado: picoCTF{c0d3b00k_455157_197a982c}
