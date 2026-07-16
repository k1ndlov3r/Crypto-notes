# Cryptographic Algorithms and Modes of Operation

## Introduction

Modern cryptography relies on a variety of encryption algorithms and operating modes to provide confidentiality, integrity, and secure communication. While block ciphers define how data is encrypted, modes of operation determine how those ciphers process messages larger than a single block. This document provides an overview of commonly used block cipher modes, stream ciphers, public-key algorithms, and cryptographic standards.

---

# Block Cipher Modes of Operation

A block cipher encrypts data in fixed-size blocks (for example, AES uses 128-bit blocks). Different modes of operation define how these blocks are processed.

---

## Electronic Codebook (ECB)

ECB is the simplest mode of operation. Each plaintext block is encrypted independently using the same encryption key.

### Characteristics

- Easy to implement
- Supports parallel encryption
- Identical plaintext blocks produce identical ciphertext blocks

### Advantages

- Fast
- Simple

### Disadvantages

- Reveals patterns in encrypted data
- Not recommended for encrypting large amounts of structured information

---

## Cipher Block Chaining (CBC)

CBC improves security by XORing each plaintext block with the previous ciphertext block before encryption.

The first block uses an **Initialization Vector (IV)** instead of a previous ciphertext block.

### Advantages

- Eliminates repeated ciphertext patterns
- More secure than ECB

### Limitations

- Encryption cannot be parallelized
- Requires a unique IV

---

## Propagating Cipher Block Chaining (PCBC)

PCBC extends CBC by propagating changes throughout the encryption process.

### Characteristics

- Small changes affect many subsequent blocks
- Primarily used in academic discussions
- Rarely implemented in modern systems

---

## Cipher Feedback (CFB)

CFB converts a block cipher into a self-synchronizing stream cipher.

### Characteristics

- Encrypts small amounts of data
- Previous ciphertext influences future encryption
- Suitable for streaming applications

---

## Output Feedback (OFB)

OFB generates a keystream independent of the plaintext.

The keystream is XORed with the plaintext to produce ciphertext.

### Advantages

- Errors do not propagate
- Suitable for noisy communication channels

---

## Counter Mode (CTR)

CTR encrypts successive counter values to generate a keystream.

### Advantages

- Very fast
- Supports parallel encryption and decryption
- Widely used with AES

---

## Initialization Vector (IV)

An Initialization Vector (IV) is a random or pseudorandom value used together with the encryption key.

### Purpose

- Prevent identical plaintext from producing identical ciphertext
- Increase randomness
- Improve security

A secure IV should be unique for every encryption operation.

---

# Stream Ciphers

Unlike block ciphers, stream ciphers encrypt data one bit or byte at a time.

They generate a pseudorandom keystream that is combined with plaintext using the XOR operation.

---

## Synchronous Stream Cipher

The keystream is generated independently of both plaintext and ciphertext.

### Characteristics

- Fast
- Efficient
- Sender and receiver must remain synchronized

---

## Self-Synchronizing Stream Cipher

The keystream depends on previous ciphertext values.

### Advantages

- Automatically resynchronizes after transmission errors
- Useful in unreliable communication channels

---

## RC4

RC4 was designed by Ron Rivest in 1987.

### Characteristics

- Software-based stream cipher
- Uses XOR between the keystream and plaintext
- Once widely deployed in SSL/TLS and WEP

### Security Status

> **⚠️ Deprecated:** RC4 is now considered insecure due to significant cryptographic weaknesses and should not be used in modern applications.

---

