### Description

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip)

### 1 Hints 

After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solución

Se descarga el archivo correspondiente el cual es un zip y entramos a su dirección de enlace y extraemos el zip, después se revisa el contenido, ejecutamos el ultimo archivo y con esto nos muestra nuestra flag: 

```cmd
jazmin@DESKTOP-1CBQJ6D:~/FIS$ wget https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip
--2025-02-17 12:51:04--  https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: ‘Addadshashanammu.zip.1’

Addadshashanammu.zip.1        100%[=================================================>]   4.41K  --.-KB/s    in 0s

2025-02-17 12:51:05 (557 MB/s) - ‘Addadshashanammu.zip.1’ saved [4520/4520]

jazmin@DESKTOP-1CBQJ6D:~/FIS$ ls
Addadshashanammu.zip                  file                  ltdis.sh.save             strings:Zone.Identifier
Addadshashanammu.zip.1                file:Zone.Identifier  ltdis.sh:Zone.Identifier  warm
Addadshashanammu.zip:Zone.Identifier  flag                  static                    warm:Zone.Identifier
enc_flag                              flag:Zone.Identifier  static:Zone.Identifier
enc_flag:Zone.Identifier              ltdis.sh              strings
jazmin@DESKTOP-1CBQJ6D:~/FIS$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet
jazmin@DESKTOP-1CBQJ6D:~/FIS$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
jazmin@DESKTOP-1CBQJ6D:~/FIS/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
jazmin@DESKTOP-1CBQJ6D:~/FIS/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}
jazmin@DESKTOP-1CBQJ6D:~/FIS/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$
```

### Resultado: picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}
