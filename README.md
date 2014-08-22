# RSA #

An implementation of the RSA algorithm in Haskell, for my college Information Security class.

## Installation ##

You need to have the [Haskell Platform](https://www.haskell.org/platform/ "Download Haskell") installed. After that, clone this repository and make the binary:

```bash
$ git clone git@github.com:aaditmshah/rsa.git
$ cd rsa
$ ghc --make keygen.hs -o keygen
$ ghc --make rsa.hs -o rsa
```

If you don't have `git` then you can simply download the [repository archive](https://github.com/aaditmshah/rsa/archive/master.zip) and unzip it.

## Usage ##

After you have made the binary you can use it as follows:

```bash
$ ./keygen
Usage: keygen number number
$ ./keygen 61 53
n: 3233
e: 3119
d: 6239
$ ./rsa
Usage: rsa number number
$ ./rsa 3119 3233 > ciphertext
Hello World!
$ ./rsa 6239 3233 < ciphertext
Hello World!
$ rm ciphertext
```

The keygen binary is used to generate the private/public key pairs. It takes two prime numbers (`p` and `q`) as arguments and returns three numbers (`n`, `e` and `d`) as results. The two key pairs are `e`-`n` and `d`-`n` where `n` is the modulus and `e` and `d` are the exponents.

The rsa binary is used to encrypt and decrypt messages using a given key pair. It takes two arguments: the exponent and the modulus which together form a key pair. Note that the value of modulus must not exceed `fromEnum (maxBound :: Char)`. On my system this is `1114111`. It's also recommended that the modulus be more than `255`.

## License ##

Since this is my college work, and since my class mates have plagiarized my work before, I have decided to take action against it:

```
Copyright (c) 2014 Aadit M Shah <aaditmshah@fastmail.fm>

Everyone is permitted to use, copy and modify this software. However distribution of the software, verbatim or modified, is not permitted without the author's non-repudiatable consent.
```