# RED

#### Description

RED, RED, RED, RED Download the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)

#### Hints

* The picture seems pure, but is it though?
* Red?Ged?Bed?Aed?
* Check whatever Facebook is called now.

## Solución

Nos dirigimos al siguiente link que es donde proviene nuestra imagen previamente descargada, entonces nos vamos a la sección `Zsteg` y copiamos la siguiente codificación:
`"cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ=="`

Y nos dirigimos al link para decodificar en `base64` e ingresamos la codificación en ASCII y con eso nos mostrara nuestra respectiva flag.

### Respuesta: picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}

## Referencias:
* https://aperisolve.com/12b8dea3ba0870bc1bd0c3ebd9686c89
* https://www.base64decode.org/