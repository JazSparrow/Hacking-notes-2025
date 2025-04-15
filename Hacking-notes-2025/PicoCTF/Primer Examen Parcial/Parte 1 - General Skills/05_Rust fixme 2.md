# Rust fixme 2

## Description

The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee? Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).

## Hints

* https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html

## Solución

Primero descargamos el archivo correspondiente y lo descomprimimos, enseguida lo ubicamos en nuestra carpeta de linux, una vez dentro, ingresaremos el siguiente comando `nano main.rs`:

```
jazmin@DESKTOP-1CBQJ6D:~$ cd FSI/
jazmin@DESKTOP-1CBQJ6D:~/FSI$ cd fixme2
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme2$ cd fixme2
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme2/fixme2$ nano main.rs
```

Y corregimos el código ya que le faltan cosas, principalmente es agregar la palabra **mut** 
en las siguientes líneas: 

```
fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?
```

```
let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
```

```
decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can>}
```

El programa completo nos queda de la siguiente manera:

```
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?

    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
    println!("{}", borrowed_string);
}

fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "0d", "c4", "60", "f2", "12",>
    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
}
```Al solucionar los errores relacionados con la mutabilidad de las variables, el código queda de la siguiente manera:

```rust
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer:Vec<u8>, borrowed_string: &mut String){ // How do we pass values to a function that we want to change?

    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    borrowed_string.push_str(&String::from_utf8_lossy(&decrypted_buffer));
    println!("{}", borrowed_string);
}

fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "0d", "c4", "60", "f2", "12",>
    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: "); // Is this variable changeable?
    decrypt(encrypted_buffer, &mut party_foul); // Is this the correct way to pass a value to a function so that it can be changed?
}
```

Después ponemos lo siguientes comandos y con esto nos dará nuestra respectiva flag:
* `cargo build`
* `cargo run`

```
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme2/fixme2/src$ cargo build
   Compiling rust_proj v0.1.0 (/home/jazmin/FSI/fixme2/fixme2)
    Finished dev [unoptimized + debuginfo] target(s) in 3.73s
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme2/fixme2/src$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.01s
     Running `/home/jazmin/FSI/fixme2/fixme2/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}
jazmin@DESKTOP-1CBQJ6D:~/FSI/fixme2/fixme2/src$
```
### Respuesta: picoCTF{4r3_y0u_h4v1n5_fun_y31?}