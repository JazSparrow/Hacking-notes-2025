# Rust fixme 1
## Description

Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag! Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).

## Hints

* Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)
* [println!](https://doc.rust-lang.org/std/macro.println.html)
* Rust has some pretty great compiler error messages. Read them maybe?

## Solución

Primero descargamos el archivo correspondiente y lo descomprimimos, enseguida lo ubicamos en nuestra carpeta de linux, una vez dentro, ingresaremos el siguiente comando `nano main.rs`:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FSI/
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd fixme1
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1$ cd fixme1
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1/fixme1$ nano main.rs
```

Y corregimos el código ya que tiene varios errores tanto como palabras incompletas y de ;
El programa nos queda de la siguiente manera:

```
use xor_cryptor::XORCryptor;

  
fn main() {

    // Key for decryption

    let key = String::from("CSUCKS"); // How do we end statements in Rust?

  

    // Encrypted flag values

    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

  

    // Convert the hexadecimal strings to bytes and collect them into a vector

    let encrypted_buffer: Vec<u8> = hex_values.iter()

        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())

        .collect();

  

    // Create decrpytion object

    let res = XORCryptor::new(&key);

    if res.is_err() {

        return; // How do we return in rust?

    }

    let xrc = res.unwrap();

  

    // Decrypt flag and print it out

    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);

    println!(

        "{}:?", // How do we print out a variable in the println function?

        String::from_utf8_lossy(&decrypted_buffer)

    );

}
```

NOTA IMPORTNTE: Nos pedirá instalar el **cargo** con el siguiente comando: 

```jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1/fixme1$ cargo build
Command 'cargo' not found, but can be installed with:

sudo snap install rustup  # version 1.27.1, or
sudo apt  install cargo   # version 1.75.0+dfsg0ubuntu1~bpo0-0ubuntu0.20.04

See 'snap info rustup' for additional versions.

jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1/fixme1$ sudo apt install cargo
[sudo] password for jazmin:
Reading package lists... Done
Building dependency tree
Reading state information... Done
```

Después ponemos lo siguientes comandos y con esto nos dará nuestra respectiva flag:
* `cargo build`
* `cargo run`

## Terminal de ejemplo

```
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd fixme1
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1$ cd fixme1
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1/fixme1$ nano main.rs
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1/fixme1$ cargo build
    Updating crates.io index
  Downloaded xor_cryptor v1.2.3
  Downloaded crossbeam-deque v0.8.5
  Downloaded either v1.13.0
  Downloaded crossbeam-utils v0.8.20
  Downloaded crossbeam-epoch v0.9.18
  Downloaded rayon-core v1.12.1
  Downloaded rayon v1.10.0
  Downloaded 7 crates (388.2 KB) in 0.67s
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/jazmin/FSI/fixme1/fixme1)
    Finished dev [unoptimized + debuginfo] target(s) in 10.31s
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1/fixme1$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.02s
     Running `target/debug/rust_proj`
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}:?
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme1/fixme1$
```
### Respuesta: picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}