# Classical Ciphers

## Introduction

Before modern cryptographic algorithms such as AES and RSA, secure communication relied on a variety of classical ciphers. These techniques were designed to conceal messages by substituting, rearranging, or transforming characters. While they are no longer considered secure, studying them provides valuable insight into the evolution of cryptography and the foundations of modern encryption.

---

## Caesar Cipher

The Caesar Cipher is one of the earliest known encryption techniques. It works by shifting each letter of the plaintext by a fixed number of positions in the alphabet.

### Example

Plaintext:

```text
HELLO
```

Shift: 3

Ciphertext:

```text
KHOOR
```

### Weaknesses

* Only 25 possible keys exist.
* Easily broken through brute force attacks.
* Preserves letter frequency patterns.

---

## Atbash Cipher

The Atbash Cipher is a substitution cipher that reverses the alphabet. The first letter is replaced with the last, the second with the second-last, and so on.

### Example

```text
A → Z
B → Y
C → X
```

Plaintext:

```text
HELLO
```

Ciphertext:

```text
SVOOL
```

### Characteristics

* No encryption key is required.
* Simple to implement.
* Offers very little security.

---

## Affine Cipher

The Affine Cipher is a mathematical substitution cipher that maps each plaintext letter to a ciphertext letter using a linear function.

### Encryption Formula

E(x)=(ax+b)\bmod m

Where:

* `m` is the alphabet size (26 for English).
* `a` and `b` are encryption keys.
* `x` is the numerical value of the plaintext letter.

### Characteristics

* More complex than the Caesar Cipher.
* Uses modular arithmetic.
* Vulnerable to frequency analysis.

---

## ROT13

ROT13 is a special case of the Caesar Cipher where every letter is rotated by 13 positions.

### Example

```text
CAT → PNG
HELLO → URYYB
```

### Characteristics

* Applying ROT13 twice returns the original message.
* Commonly used to obscure text rather than provide security.

---

## Scytale Cipher

The Scytale Cipher was used in ancient Greece, particularly by the Spartans.

A strip of parchment was wrapped around a rod of a specific diameter. The sender wrote the message across the rod, and only someone with a rod of the same size could reconstruct the original message.

### Characteristics

* One of the earliest transposition ciphers.
* Relies on a physical key rather than a mathematical one.

---

## Vigenère Cipher

The Vigenère Cipher is a polyalphabetic substitution cipher that uses a keyword to determine letter shifts.

### Example

Plaintext:

```text
CAT
```

Keyword:

```text
HORSE
```

Each plaintext letter is encrypted using a different alphabet determined by the corresponding key letter.

### Advantages

* More resistant to frequency analysis than monoalphabetic ciphers.
* Was considered highly secure for centuries.

### Weaknesses

* Vulnerable to Kasiski Examination and other cryptanalytic techniques.

---

## Playfair Cipher

The Playfair Cipher encrypts pairs of letters rather than individual characters.

### Characteristics

* Uses a 5×5 matrix generated from a keyword.
* Encrypts digraphs (pairs of letters).
* More secure than simple substitution ciphers.

### Example Use

```text
HI DE TH EG OL DI NT HE TR EE ST UM P
```

---

## Polybius Square

The Polybius Square converts letters into coordinates within a grid.

### Example

```text
A = 11
B = 12
C = 13
```

A letter is represented by its row and column positions.

### Characteristics

* Converts text into numerical representations.
* Frequently used as a component in more advanced ciphers.

---

## ADFGVX Cipher

The ADFGVX Cipher combines substitution and transposition techniques.

### Characteristics

* Developed for military communication.
* Uses a 6×6 Polybius-style square.
* Incorporates columnar transposition.
* Considerably stronger than earlier classical ciphers.

---

## Homophonic Substitution Cipher

In a homophonic substitution cipher, a single plaintext letter may map to multiple ciphertext symbols.

### Example

The letter **E** might be represented by:

```text
12, 34, 56, 78
```

### Advantages

* Reduces the effectiveness of frequency analysis.
* Produces a more uniform ciphertext distribution.

---

## Null Cipher

A Null Cipher hides a secret message inside an innocent-looking message.

### Example

A predefined pattern may instruct the recipient to extract specific letters from a normal sentence to reveal the hidden message.

### Characteristics

* Relies on concealment rather than encryption.
* Often used in historical espionage.

---

## Book Cipher

A Book Cipher uses a shared book as the encryption key.

### Example

```text
3,5,12
```

This may refer to:

* Page 3
* Line 5
* Word 12

### Characteristics

* Requires both parties to possess the same book.
* Difficult to decipher without knowledge of the reference text.

---

## Rail Fence Cipher

The Rail Fence Cipher is a transposition cipher that rearranges characters across multiple rows.

### Example

Plaintext:

```text
ATTACKATDAWN
```

Written in a zigzag pattern and then read row by row.

### Characteristics

* Does not alter characters.
* Only changes their positions.
* Easy to break without additional protections.

---

## Vernam Cipher

The Vernam Cipher introduced the concept of combining plaintext with a key using the XOR operation.

### Characteristics

* Foundation of the One-Time Pad.
* Uses a random key stream.
* When implemented correctly with a truly random key used only once, it provides perfect secrecy.

### Importance

The Vernam Cipher played a significant role in the development of modern stream ciphers and secure communication systems.

---

## Conclusion

Classical ciphers represent the historical foundations of cryptography. Although most are insecure by modern standards, they demonstrate important concepts such as substitution, transposition, key management, and cryptanalysis. Understanding these techniques helps build a stronger appreciation for modern cryptographic systems and security practices.
