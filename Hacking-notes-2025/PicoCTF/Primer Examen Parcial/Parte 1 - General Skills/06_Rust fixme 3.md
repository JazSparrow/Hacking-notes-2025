# Rust fixme 3

## Description

Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).

## Hints

* Read the comments...darn it!

## Solución

Primero descargamos el archivo correspondiente y lo descomprimimos, enseguida lo ubicamos en nuestra carpeta de linux, una vez dentro, ingresaremos el siguiente comando `nano main.rs`:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FSI/
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd fixme3
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme3$ cd fixme3
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme3/fixme3$ cd src
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme3/fixme3/src$ nano main.rs
```

Corregimos el código, en este caso solo seria quitarle los `//` que hay en la parte `unsafe` quedando esa parte de la siguiente manera:

```
 unsafe {
        // Decrypt the flag operations
        let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);

        // Creating a pointer
        let decrypted_ptr = decrypted_buffer.as_ptr();
        let decrypted_len = decrypted_buffer.len();

        // Unsafe operation: calling an unsafe function that dereferences a raw pointer
        let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);

        borrowed_string.push_str(&String::from_utf8_lossy(decrypted_slice));
     }
```

Después ingresamos lo siguientes comandos y con esto nos dará nuestra respectiva flag:
* `cargo build`
* `cargo run`

```
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme3/fixme3/src$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/jazmin/FSI/fixme3/fixme3)
    Finished dev [unoptimized + debuginfo] target(s) in 7.19s
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme3/fixme3/src$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.02s
     Running `/home/jazmin/FSI/fixme3/fixme3/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme3/fixme3/src$
```
### Respuesta: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}