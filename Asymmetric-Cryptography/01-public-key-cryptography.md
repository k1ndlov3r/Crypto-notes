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

---
