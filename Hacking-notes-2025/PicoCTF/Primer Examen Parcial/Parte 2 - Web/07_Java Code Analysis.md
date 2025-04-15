# Java Code Analysis!?!

## Description

BookShelf Pico, my premium online book-reading service. I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book! Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/484/bookshelf-pico.zip). Website can be accessed [here!](http://saturn.picoctf.net:62553/).

## Hints

* Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
*  The 'role' and 'userId' fields in the JWT can be of interest to you!
* The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
* Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

## Solución

Entramos con user como usuario y contraseña en el link que nos proporcionan, una vez dentro nos iremos a la imagen que dice **FLAG** y daremos clic derecho y seleccionamos **inspeccionar**, nos iremos a **red** y daremos en **recargar** y seleccionamos y después nos vamos a la sección y copiamos el encriptado. 

![[Pasted image 20250414000726.png]]

Enseguida entraremos a la página de `jwt.io` y ahi pegaremos nuestro encriptado y en decodificar modificaremos las siguientes cosas:
#### Decoded
```
PAYLOAD: DATA
{
  "role": "Admin",
  "iss": "bookshelf",
  "exp": 1745215565,
  "iat": 1744610765,
  "userId": 2,
  "email": "admin"
}
```

```
VERIFY SIGNATURE
1234
```

En **Encoded** nos muestra ya desencriptado nuestro mensaje y lo copiaremos:
#### Encoded
```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJyb2xlIjoiQWRtaW4iLCJpc3MiOiJib29rc2hlbGYiLCJleHAiOjE3NDUyMTU1NjUsImlhdCI6MTc0NDYxMDc2NSwidXNlcklkIjoyLCJlbWFpbCI6ImFkbWluIn0.oAdI8IUyD1vlGAPkJDyAFutarIIhK0Q1aoLXD_6GaJQ
```

Después iremos a la sección **Almacenamiento** y damos clic en **Almacenamiento local** y pegamos nuestro **Encoded** en el **Value** y el **Decoded** `PAYLOAD: DATA` donde especifica nuestro nuevo admin, y damos recargar y nos mostrara nuestra respectiva flag:

![[Pasted image 20250414000916.png]]
![[Pasted image 20250414001036.png]]
### Respuesta: picoCTF{w34k_jwt_n0t_g00d_6e5d7df5}

## Referencias
https://jwt.io/