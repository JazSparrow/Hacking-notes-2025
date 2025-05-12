# waves over lambda

#### Description

We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 43522`.

#### Hints

* Flag is not in the usual flag format

## Solución

En nuestra terminal de ubuntu ingresamos el nc previamente proporcionado, y nos mostrara un cifrado, entonces usaremos el **cifrado por sustitución** con en link de `Substitution Solver` y entonces pegamos el cifrado y nos muestra nuestra respectiva flag en la salida.

## Terminal de ejemplo:

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ mkdir waves
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd waves
jazmin@DESKTOP-1CBQJ6D:~/FSI/waves$ nc jupiter.challenges.picoctf.org 43522
-------------------------------------------------------------------------------
rjqystol xksk gl hjws ipty - iskvwkqrh_gl_r_jzks_ptfuct_jyiftwqsti
-------------------------------------------------------------------------------
tpkekh ihjcjsjzgorx dtstftajz btl oxk oxgsc ljq ji ihjcjs mtzpjzgorx dtstftajz, t ptqc jbqks bkpp dqjbq gq jws cglosgro gq xgl jbq cth, tqc logpp skfkfukskc tfjqy wl jbgqy oj xgl ypjjfh tqc ostygr cktox, bxgrx xtmmkqkc oxgsokkq hktsl tyj, tqc bxgrx g lxtpp cklrsguk gq gol msjmks mptrk. ijs oxk msklkqo g bgpp jqph lth oxto oxgl ptqcjbqksijs lj bk wlkc oj rtpp xgf, tpoxjwyx xk xtscph lmkqo t cth ji xgl pgik jq xgl jbq klotokbtl t lostqyk ohmk, hko jqk mskooh iskvwkqoph oj uk fko bgox, t ohmk tunkro tqc zgrgjwl tqc to oxk ltfk ogfk lkqlkpkll. uwo xk btl jqk ji oxjlk lkqlkpkll mksljql bxj tsk zksh bkpp rtmtupk ji pjjdgqy tioks oxkgs bjspcph tiitgsl, tqc, tmmtskqoph, tioks qjoxgqy kplk. ihjcjs mtzpjzgorx, ijs gqlotqrk, ukytq bgox qkeo oj qjoxgqy; xgl klotok btl ji oxk lftppklo; xk stq oj cgqk to joxks fkq'l otupkl, tqc itlokqkc jq oxkf tl t ojtch, hko to xgl cktox go tmmktskc oxto xk xtc t xwqcskc oxjwltqc sjwupkl gq xtsc rtlx. to oxk ltfk ogfk, xk btl tpp xgl pgik jqk ji oxk fjlo lkqlkpkll, itqotlogrtp ikppjbl gq oxk bxjpk cglosgro. g skmkto, go btl qjo lowmgcgohoxk ftnjsgoh ji oxklk itqotlogrtp ikppjbl tsk lxskbc tqc gqokppgykqo kqjwyxuwo nwlo lkqlkpkllqkll, tqc t mkrwpgts qtogjqtp ijsf ji go.
```

![[Pasted image 20250512155939.png]]
### Respuesta: frequency_is_c_over_lambda_ogfmaunraf

## Referencias:
https://www.guballa.de/substitution-solver