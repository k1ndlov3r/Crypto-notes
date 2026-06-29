# Feistel Network

## Introduction

The **Feistel Network** (also called a **Feistel Cipher**) is one of the most influential structures in modern cryptography. It is a design model used to build many symmetric block ciphers.

The structure was developed by **Horst Feistel** while working at IBM in the early 1970s and later became the foundation of the **Data Encryption Standard (DES)**.

One of the biggest advantages of a Feistel Network is that **the same algorithm can be used for both encryption and decryption**. The only difference is that the round keys are applied in reverse order during decryption.

---

# How a Feistel Network Works

A plaintext block is divided into two equal halves:

- Left Half (L)
- Right Half (R)

Each encryption round performs the following operations:

1. The right half is processed using a round function.
2. The output is XORed with the left half.
3. The two halves are swapped.
4. The process repeats for multiple rounds.

---

## Feistel Structure

```text
                 Plaintext
                     │
          ┌──────────┴──────────┐
          │                     │
      Left (L0)             Right (R0)
          │                     │
          │                 +-----------+
          │                 | F Function|
          │                 +-----------+
          │                     │
          │                  Round Key
          │                     │
          └────── XOR ◄─────────┘
                     │
             New Right Half
                     │
                Swap Halves
                     │
              Next Encryption Round
```

This process continues until all rounds have been completed.

---

# Mathematical Representation

For every round:

```text
Li+1 = Ri

Ri+1 = Li XOR F(Ri, Ki)
```

Where:

- **Li** = Left half
- **Ri** = Right half
- **Ki** = Round Key
- **F()** = Round Function

---

# Why Swap the Halves?

The swap operation ensures that both halves of the plaintext are processed over multiple rounds.

Without swapping:

- Only one side would be transformed.
- Diffusion would be weak.
- Security would decrease significantly.

---

# Round Function (F Function)

The **Round Function**, often called the **F Function**, is the heart of every Feistel cipher.

Its purpose is to transform the input into a highly unpredictable output.

Depending on the algorithm, the F Function may perform:

- Expansion
- XOR
- Substitution
- Permutation
- Rotation
- Bit Mixing

A stronger round function generally results in stronger encryption.

---

# Round Keys

Instead of using the same key directly in every round, the main encryption key is transformed into multiple **Round Keys**.

Each encryption round uses a different round key.

Example:

```text
Master Key

↓

K1

↓

K2

↓

K3

↓

...

↓

Kn
```

Using different keys for each round greatly increases security.

---

# Key Schedule

## What is a Key Schedule?

A **Key Schedule** is the algorithm responsible for generating the round keys from the original secret key.

Rather than using the same key repeatedly, the key schedule creates multiple unique keys.

---

## Why is a Key Schedule Important?

It provides:

- Better security
- Increased randomness
- Resistance against cryptanalysis
- Different keys for every round

---

## Example

Suppose the master key is:

```text
1011001101010110
```

The key schedule generates:

```text
Round 1 → K1

Round 2 → K2

Round 3 → K3

...

Round N → Kn
```

Each key is slightly different.

---

# S-Box (Substitution Box)

## What is an S-Box?

An **S-Box (Substitution Box)** performs **non-linear substitution**.

It replaces one binary value with another according to a predefined lookup table.

This introduces **Confusion**, making it difficult to discover any relationship between:

- Plaintext
- Ciphertext
- Secret Key

---

## Example

Suppose the S-Box contains:

| Input | Output |
|--------|--------|
| 0000 | 1110 |
| 0001 | 0100 |
| 0010 | 1101 |
| 0011 | 0001 |

Input:

```text
0010
```

Output:

```text
1101
```

The transformation is not mathematical—it is based on a predefined lookup table.

---

## Why are S-Boxes Important?

Without S-Boxes:

- Encryption would be mostly linear.
- Attackers could discover patterns.
- Cryptanalysis would become much easier.

S-Boxes are one of the primary sources of security in many block ciphers.

---

# P-Box (Permutation Box)

## What is a P-Box?

A **Permutation Box (P-Box)** rearranges bits without changing their values.

Unlike an S-Box, a P-Box does **not** substitute bits.

Instead, it changes their positions.

Example:

```text
Input

10110011

↓

Permutation

11100110
```

---

## Purpose of a P-Box

P-Boxes provide:

- Diffusion
- Bit spreading
- Increased randomness
- Resistance against statistical attacks

---

# S-Box vs P-Box

| Feature | S-Box | P-Box |
|----------|-------|--------|
| Operation | Substitution | Permutation |
| Changes Bit Values | Yes | No |
| Changes Bit Positions | No | Yes |
| Shannon Principle | Confusion | Diffusion |

Modern block ciphers often combine both S-Boxes and P-Boxes to achieve strong security.

---

# Strict Avalanche Criterion (SAC)

## What is SAC?

The **Strict Avalanche Criterion (SAC)** measures how sensitive an encryption algorithm is to changes in its input.

A secure cipher should produce a significantly different ciphertext even if only **one input bit** changes.

Ideally:

> Flipping one input bit should change approximately **50% of the output bits**.

---

## Example

Original Plaintext

```text
11001100
```

Encrypted

```text
10100111
```

Now change one bit:

```text
11001101
```

New Ciphertext

```text
01111010
```

Although only one input bit changed, the ciphertext is almost completely different.

---

# Bit Independence Criterion (BIC)

## What is BIC?

The **Bit Independence Criterion (BIC)** measures whether output bits change independently of one another.

Changing one input bit should not create predictable relationships between output bits.

Good algorithms satisfy both:

- Avalanche Effect
- Bit Independence Criterion

---

# Encryption vs Decryption

One of the greatest strengths of a Feistel Network is that encryption and decryption use the **same algorithm**.

Encryption:

```text
K1 → K2 → K3 → ... → Kn
```

Decryption:

```text
Kn → ... → K3 → K2 → K1
```

Only the order of the keys changes.

This makes Feistel ciphers simpler to implement.

---

# Algorithms That Use a Feistel Network

Examples include:

- DES
- Triple DES
- Blowfish
- Twofish
- CAST-128
- TEA
- XTEA
- Camellia (Feistel-like)

---

# Algorithms That Do NOT Use a Feistel Network

Not every block cipher uses the Feistel structure.

Examples include:

- AES
- Serpent
- PRESENT
- Square

These algorithms use a **Substitution-Permutation Network (SPN)** instead.

---

# Advantages of a Feistel Network

- Same algorithm for encryption and decryption
- Easy hardware implementation
- Flexible design
- Efficient key scheduling
- Proven security when combined with strong round functions

---

# Disadvantages

- Usually requires many encryption rounds.
- Security depends heavily on the quality of the round function.
- Older Feistel-based algorithms such as DES have become obsolete due to small key sizes.

---

# Real-World Applications

Feistel Networks are used in:

- DES
- Triple DES
- Blowfish
- Twofish
- Password managers
- Legacy banking systems
- Embedded devices

Although AES has replaced DES in most modern systems, Feistel structures remain an important concept in cryptography.

---

# Key Takeaways

- A Feistel Network is a design model for symmetric block ciphers.
- Plaintext is divided into left and right halves.
- Each round applies a round function, XOR, and a swap.
- A key schedule generates unique round keys.
- S-Boxes provide **Confusion**.
- P-Boxes provide **Diffusion**.
- SAC measures the Avalanche Effect.
- BIC measures output bit independence.
- Encryption and decryption use the same algorithm; only the key order changes.
- DES, Blowfish, Twofish, and TEA are Feistel-based ciphers.
- AES is **not** a Feistel cipher—it uses a Substitution-Permutation Network (SPN).

---
