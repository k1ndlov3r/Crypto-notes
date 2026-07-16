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

# Public-Key Cryptography

Public-key cryptography uses separate public and private keys for encryption, decryption, and digital signatures.

---

## Diffie–Hellman (DH)

Diffie–Hellman is a key exchange protocol.

It enables two parties to establish a shared secret over an insecure communication channel.

### Key Points

- Introduced in 1976 by Whitfield Diffie and Martin Hellman
- Not an encryption algorithm
- Used to establish shared secret keys

---

## RSA

RSA is one of the most widely used public-key cryptographic algorithms.

It is named after Ron Rivest, Adi Shamir, and Leonard Adleman.

### Applications

- Encryption
- Digital Signatures
- Secure Key Exchange

### Security

RSA's security depends on the computational difficulty of factoring very large integers.

---

## MQV (Menezes–Qu–Vanstone)

MQV is an authenticated key agreement protocol based on the Diffie–Hellman algorithm.

### Features

- Mutual authentication
- Efficient key agreement
- Standardized in IEEE P1363

---

## Elliptic Curve Cryptography (ECC)

Elliptic Curve Cryptography (ECC) provides security comparable to RSA while requiring much smaller key sizes.

### Common ECC Algorithms

- Elliptic Curve Diffie–Hellman (ECDH)
- Elliptic Curve Digital Signature Algorithm (ECDSA)
- Elliptic Curve Integrated Encryption Scheme (ECIES)

### Advantages

- Smaller keys
- Faster computations
- Lower memory usage
- Widely used in TLS, cryptocurrencies, and mobile devices

---

## ElGamal

ElGamal is a public-key cryptosystem based on the Diffie–Hellman key exchange principle.

### Applications

- Encryption
- Digital Signatures
- GNU Privacy Guard (GPG)

---

## Perfect Forward Secrecy (PFS)

Perfect Forward Secrecy (PFS) ensures that the compromise of a server's long-term private key does **not** compromise previously established session keys.

This property is commonly achieved using ephemeral key exchange protocols such as ECDHE.

---

# Cryptographic Standards

Several standards define secure cryptographic implementations.

## FIPS 140

Defines the security requirements for cryptographic modules.

---

## FIPS 186

Digital Signature Standard (DSS).

---

## FIPS 197

Defines the Advanced Encryption Standard (AES).

---

## FIPS 201

Defines the Personal Identity Verification (PIV) standard used by the U.S. Federal Government.

---

# Summary

Modern cryptography combines secure algorithms with appropriate modes of operation to protect data. While some older techniques such as **ECB** and **RC4** are now considered insecure, modern approaches like **AES-CBC**, **AES-CTR**, **RSA**, **Diffie–Hellman**, and **Elliptic Curve Cryptography (ECC)** continue to play a critical role in securing today's digital communications.

Understanding these concepts provides a strong foundation for cybersecurity professionals working in penetration testing, digital forensics, incident response, cloud security, and secure software development.
