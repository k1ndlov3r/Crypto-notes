# Symmetric Encryption Algorithms

## Introduction

Symmetric encryption algorithms use a **single shared secret key** for both encryption and decryption. They are significantly faster than asymmetric algorithms and are widely used for protecting data at rest and data in transit.

Over the years, many symmetric algorithms have been developed. Some are now considered insecure, while others remain industry standards.

---

# Data Encryption Standard (DES)

## Overview

The **Data Encryption Standard (DES)** was developed by IBM in the early 1970s and later adopted as a federal standard by NIST in 1977.

DES became one of the most widely used encryption algorithms in the world before eventually becoming obsolete due to its small key size.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 64 bits |
| Key Size | 56 bits (64 bits including parity) |
| Structure | Feistel Network |
| Number of Rounds | 16 |
| Standard | FIPS 46 |

---

## Advantages

- Fast in hardware
- Well studied
- Simple implementation
- Historical significance

---

## Disadvantages

- 56-bit key is too small
- Vulnerable to brute-force attacks
- Considered insecure today

---

## Why DES Failed

When DES was introduced, a 56-bit key was considered secure.

Today, modern hardware can brute-force all possible DES keys in a relatively short time.

For this reason, DES should **never** be used for protecting sensitive information.

---

# Triple DES (3DES)

## Overview

Triple DES (3DES) was developed as a temporary replacement for DES.

Instead of encrypting data once, it applies DES **three times**.

---

## Encryption Process

```text
Plaintext
     │
     ▼
Encrypt (K1)
     │
     ▼
Decrypt (K2)
     │
     ▼
Encrypt (K3)
     │
     ▼
Ciphertext
```

This process is known as **EDE (Encrypt-Decrypt-Encrypt)**.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 64 bits |
| Effective Key Size | 112 or 168 bits |
| Structure | Feistel Network |
| Rounds | 48 (16 × 3) |

---

## Advantages

- Much stronger than DES
- Easy migration from existing DES systems
- Well understood

---

## Disadvantages

- Slow
- Small block size
- Vulnerable to birthday attacks
- Deprecated by NIST

---

# Advanced Encryption Standard (AES)

## Overview

The **Advanced Encryption Standard (AES)** is the modern encryption standard adopted by NIST in 2001.

AES replaced DES because it provides significantly stronger security and better performance.

Unlike DES, AES is **not** a Feistel cipher.

It uses a **Substitution-Permutation Network (SPN)**.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 128 bits |
| Key Sizes | 128, 192, 256 bits |
| Structure | SPN |
| Standard | FIPS 197 |

---

## AES Rounds

| Key Size | Rounds |
|----------|--------|
| AES-128 | 10 |
| AES-192 | 12 |
| AES-256 | 14 |

---

## AES Encryption Steps

Each round performs several operations:

1. SubBytes
2. ShiftRows
3. MixColumns *(except final round)*
4. AddRoundKey

---

## Advantages

- Extremely secure
- Fast in software and hardware
- Worldwide standard
- Resistant to known practical attacks
- Supported by AES-NI hardware acceleration

---

## Applications

AES is used in:

- HTTPS
- WPA2/WPA3
- VPNs
- BitLocker
- VeraCrypt
- SSH
- TLS
- Government systems

---

# Blowfish

## Overview

Blowfish was designed by **Bruce Schneier** in 1993 as a free alternative to DES.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 64 bits |
| Key Size | 32–448 bits |
| Structure | Feistel Network |
| Rounds | 16 |

---

## Advantages

- Fast
- Free to use
- Flexible key sizes
- Strong security

---

## Disadvantages

- 64-bit block size
- Replaced by newer algorithms

---

# Twofish

## Overview

Twofish is the successor to Blowfish and was one of the finalists in the AES competition.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 128 bits |
| Key Sizes | 128, 192, 256 bits |
| Structure | Feistel-like |
| Rounds | 16 |

---

## Advantages

- Very secure
- Flexible
- Efficient
- Publicly available

---

## Applications

Used in:

- VeraCrypt
- File encryption
- Embedded systems

---

# Serpent

## Overview

Serpent was another AES finalist.

Its designers prioritized **security over speed**.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 128 bits |
| Key Sizes | 128, 192, 256 bits |
| Structure | SPN |
| Rounds | 32 |

---

## Advantages

- Extremely secure
- Conservative design
- Strong resistance against cryptanalysis

---

## Disadvantages

- Slower than AES

---

# IDEA

## Overview

The **International Data Encryption Algorithm (IDEA)** was introduced in 1991.

It became famous for its use in early versions of **PGP (Pretty Good Privacy)**.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 64 bits |
| Key Size | 128 bits |
| Rounds | 8.5 |

---

## Advantages

- Strong mathematical design
- Good security

---

## Disadvantages

- Patented in the past
- Less commonly used today

---

# CAST-128

## Overview

CAST-128 is a symmetric block cipher developed by Carlisle Adams and Stafford Tavares.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 64 bits |
| Key Size | 40–128 bits |
| Structure | Feistel Network |
| Rounds | 12 or 16 |

---

# TEA (Tiny Encryption Algorithm)

## Overview

TEA is a lightweight encryption algorithm designed for simplicity.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 64 bits |
| Key Size | 128 bits |
| Structure | Feistel Network |
| Rounds | 64 Feistel rounds (32 cycles) |

---

## Advantages

- Small implementation
- Easy to understand
- Fast

---

## Disadvantages

- Equivalent key attacks
- Related-key attacks

---

# XTEA

XTEA is an improved version of TEA that fixes several weaknesses found in the original design.

---

# Skipjack

## Overview

Skipjack was developed by the **U.S. National Security Agency (NSA)**.

It was originally designed for the Clipper Chip initiative.

---

## Features

| Property | Value |
|----------|-------|
| Block Size | 64 bits |
| Key Size | 80 bits |
| Structure | Unbalanced Feistel Network |
| Rounds | 32 |

---

## Why It Failed

- Secret design initially
- Public distrust
- Small key size
- Eventually became obsolete

---

# Algorithm Comparison

| Algorithm | Block Size | Key Size | Structure | Status |
|------------|-----------|----------|-----------|--------|
| DES | 64 bits | 56 bits | Feistel | ❌ Obsolete |
| 3DES | 64 bits | 112/168 bits | Feistel | ⚠ Deprecated |
| AES | 128 bits | 128/192/256 bits | SPN | ✅ Recommended |
| Blowfish | 64 bits | Up to 448 bits | Feistel | ⚠ Legacy |
| Twofish | 128 bits | Up to 256 bits | Feistel-like | ✅ Secure |
| Serpent | 128 bits | Up to 256 bits | SPN | ✅ Secure |
| IDEA | 64 bits | 128 bits | Lai-Massey | ⚠ Legacy |
| CAST-128 | 64 bits | Up to 128 bits | Feistel | ⚠ Legacy |
| TEA | 64 bits | 128 bits | Feistel | ❌ Not Recommended |
| XTEA | 64 bits | 128 bits | Feistel | ⚠ Limited Use |
| Skipjack | 64 bits | 80 bits | Feistel | ❌ Obsolete |

---

# Which Algorithms Should Be Used Today?

### Recommended

- AES-128
- AES-192
- AES-256
- Twofish
- Serpent
- ChaCha20 *(Stream Cipher)*

### Avoid

- DES
- 3DES
- RC4
- Skipjack
- TEA

---

# Interview Questions

### Why did AES replace DES?

Because DES uses a 56-bit key, making it vulnerable to brute-force attacks.

---

### Is AES a Feistel cipher?

No.

AES uses a **Substitution-Permutation Network (SPN)**.

---

### Why is 3DES deprecated?

- Slow
- 64-bit block size
- Vulnerable to modern attacks
- Better alternatives exist

---

### Which symmetric algorithm is most widely used today?

AES.

---

### Which algorithm won the AES competition?

Rijndael, which became the Advanced Encryption Standard (AES).

---

# Key Takeaways

- DES is obsolete.
- 3DES is deprecated.
- AES is the current industry standard.
- Blowfish is secure but largely replaced.
- Twofish remains secure.
- Serpent prioritizes security over speed.
- IDEA and CAST are legacy algorithms.
- TEA has known weaknesses.
- AES should be the default choice for new applications.

---

# Further Reading

- FIPS 46-3 (DES)
- FIPS 197 (AES)
- NIST Cryptographic Standards
- Bruce Schneier – *Applied Cryptography*
- EC-Council Certified Encryption Specialist (ECES)
