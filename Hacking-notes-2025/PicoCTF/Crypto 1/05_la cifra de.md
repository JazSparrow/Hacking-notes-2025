# la cifra de

#### Description

I found this cipher in an old book. Can you figure out what it says? Connect with `nc jupiter.challenges.picoctf.org 58295`.

#### Hints

* There are tools that make this easy.
* Perhaps looking at history will help

## Solución

Nos dirigimos a nuestra terminal de ubuntu y una vez ahí pegamos nuestro nc proporcionado anteriormente y después nos muestra un mensaje encriptado.

Después nos dirigimos al link de **Cyberchef** y en **Recipe** seleccionamos `Vigenere Decode` e ingresamos el mensaje encriptado y en la **Key** escribimos `flag` y nos mostrara nuestra respectiva flag.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ mkdir lacifrade
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd lacifrade
jazmin@DESKTOP-1CBQJ6D:~/FSI/lacifrade$ nc jupiter.challenges.picoctf.org 58295
Encrypted message:
﻿Ne iy nytkwpsznyg nth it mtsztcy vjzprj zfzjy rkhpibj nrkitt ltc tnnygy ysee itd tte cxjltk

Ifrosr tnj noawde uk siyyzre, yse Bnretèwp Cousex mls hjpn xjtnbjytki xatd eisjd

Iz bls lfwskqj azycihzeej yz Brftsk ip Volpnèxj ls oy hay tcimnyarqj dkxnrogpd os 1553 my Mnzvgs Mazytszf Merqlsu ny hox moup Wa inqrg ipl. Ynr. Gotgat Gltzndtg Gplrfdo

Ltc tnj tmvqpmkseaznzn uk ehox nivmpr g ylbrj ts ltcmki my yqtdosr tnj wocjc hgqq ol fy oxitngwj arusahje fuw ln guaaxjytrd catizm tzxbkw zf vqlckx hizm ceyupcz yz tnj fpvjc hgqqpohzCZK{m311a50_0x_a1rn3x3_h1ah3xf966878l}

Tnj qixxe wkqw-duhfmkseej ipsiwtpznzn uk l puqjarusahjeii htpnjc hubpvkw, hay rldk fcoaso 1467 be Qpot Gltzndtg Fwbkwei.

Zmp Volpnèxj Nivmpr ox ehkwpfuwp surptorps ifwlki ehk Fwbkwei Jndc uw Llhjcto Htpnjc.

It 1508, Ozhgsyey Ycizmpmozd itapnzjo tnj do-ifwlki eahzwa xjntg (f xazwtx uk dhokeej fwpnfmezx) ehgy hoaqo lgypr hj l cxneiifw curaotjyt uk ehk Atgksèce Inahkw.

Merqlsu’x deityd htzkrje avupaxjo it 1555 fd a itytosfaznzn uk ehk ktryy. Ehk qzwkw saraps uk ehk fwpnfmezx lrk szw ymtfzjo rklflgwwy, hze tnj llvmlbkyd ati ehk nydkc wezypry fce sniej gj mkfys uk l mtjxotnn kkd ahxfde, cmtcn hln hj oilkprkse woys eghs cuwceyuznjjyt.
```

![[Pasted image 20250512151846.png]]

### Respuesta: picoCTF{b311a50_0r_v1gn3r3_c1ph3ra966878a}