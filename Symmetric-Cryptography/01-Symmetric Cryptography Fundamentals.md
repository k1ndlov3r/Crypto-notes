## **Symmetric Cryptography Fundamentals** 

## **Introduction** 

Symmetric cryptography, also known as **secret-key cryptography** , is one of the oldest and most widely used encryption techniques. It uses a **single shared key** for both encryption and decryption. 

Because the same key is used by both the sender and receiver, the key must be exchanged securely before communication begins. 

Symmetric cryptography is significantly **faster** than asymmetric cryptography, making it the preferred choice for encrypting large amounts of data. 

## **Learning Objectives** 

After reading this note, you should understand: 

- What symmetric cryptography is 

- Information theory fundamentals 

- Entropy 

- Hamming Distance 

- Hamming Weight 

- Claude Shannon's contribution to cryptography 

- Confusion and Diffusion 

- Avalanche Effect 

- Kerckhoffs's Principle 

## **What is Symmetric Cryptography?** 

Symmetric cryptography is an encryption technique where the **same secret key** is used for both encryption and decryption. 

## **Encryption** 

```
Ciphertext = Encrypt(Plaintext, Secret Key)
```


## **Decryption** 

```
Plaintext = Decrypt(Ciphertext, Secret Key)
```

Mathematically, 

```
C = E(K, P)
P = D(K, C)
```

Where: 

- **P** = Plaintext 

- **C** = Ciphertext 

- **K** = Secret Key 

- **E()** = Encryption Function 

- **D()** = Decryption Function 

## **How Symmetric Encryption Works** 

```
          Secret Key
              │
              ▼
Plaintext ──► Encryption ──► Ciphertext
                                   │
                                   ▼
                          Decryption
                                   │
                              Secret Key
                                   │
                                   ▼
                              Plaintext
```

Both parties **must possess the same secret key** . 

## **Advantages** 

- Extremely fast 

- Efficient for encrypting large files 

- Requires less computational power 


- Widely supported in hardware and software • Used in almost every secure communication protocol 

## **Disadvantages** 

- Secure key exchange is required. 

- Poor scalability (each pair of users needs a unique key). 

- If the key is compromised, all encrypted data can be decrypted. 

- Does not provide non-repudiation. 

## **Where is Symmetric Encryption Used?** 

Symmetric cryptography is widely used in: 

- HTTPS (after the TLS handshake) 

- VPNs 

- SSH 

- WPA2/WPA3 Wi-Fi security 

- BitLocker 

- VeraCrypt 

- ZIP and 7z encryption 

- Database encryption 

- Full disk encryption 

## **Information Theory** 

Information Theory is the mathematical study of **information, communication, and uncertainty** . 

Modern cryptography is heavily based on information theory. 

The field was pioneered by **Claude Shannon** , often called the **Father of Information Theory** . 

In 1949, Shannon published the landmark paper: 

_Communication Theory of Secrecy Systems_ 

This paper laid the mathematical foundation for modern cryptography. 
 

## **Entropy** 

Entropy measures the **amount of uncertainty or randomness** in a message. 

Higher entropy means: 

- Less predictable data 

- Stronger randomness 

- Better cryptographic security 

Lower entropy means: 

- More predictable data 

- Easier to guess 

- Weaker security 

The entropy of a random variable is defined as: 

```
H(X) = -Σ Pi log₂(Pi)
```

Where: 

- **H(X)** = Entropy 

- **Pi** = Probability of each event 

## **Example** 

Random password: 

```
P@9xL#2q
```

High entropy. 

Weak password: 

```
password123
```

Low entropy. 


## **Hamming Distance** 

The **Hamming Distance** is the number of positions where two equal-length strings differ. 

Example: 

```
10110101
10011101
```

Different bits: 

```
00101000
```

Hamming Distance = **2** 

## **Why is Hamming Distance Important?** 

It is used in: 

- Error detection 

- Error correction 

- Cryptography 

- Coding theory 

- Digital communications 

## **Hamming Weight** 

Hamming Weight is the **number of 1s in a binary value** . 

Example: 

```
10110110
```

Contains five **1s** . 

Therefore, 
 

```
Hamming Weight = 5
```

It is also known as: 

- Population Count 

- Popcount 

## **Claude Shannon** 

Claude Shannon is widely regarded as the **Father of Modern Cryptography** . 

His contributions include: 

- Information Theory 

- Entropy 

- Confusion 

- Diffusion 

- Mathematical foundations of secure communication 

Many modern encryption algorithms are based on Shannon's principles. 

## **Shannon's Principles** 

Modern symmetric encryption relies on two important concepts: 

- Confusion • Diffusion 

Together they make encrypted data resistant to cryptanalysis. 

## **Confusion** 

Confusion hides the relationship between: 

- Plaintext 

- Ciphertext 

- Encryption key 

The goal is to make it extremely difficult for an attacker to derive the secret key from the ciphertext. 
 

Confusion is mainly achieved using: 

- Substitution 

- S-Boxes 

## **Diffusion** 

Diffusion spreads the influence of a single plaintext bit across many ciphertext bits. 

Changing one plaintext character should affect many output bits. 

This makes statistical attacks much more difficult. 

Diffusion is mainly achieved using: 

- Permutations 

- P-Boxes 

- Multiple encryption rounds 

## **Avalanche Effect** 

A secure encryption algorithm should exhibit a strong **Avalanche Effect** . 

A tiny change in the plaintext or key should produce a **completely different ciphertext** . 

## **Example** 

Plaintext: 

```
HELLO
```

Encrypted: 

```
9F8C1A...
```

Now change one letter: 

```
HELLo
```


Encrypted: 

```
3A2E7F...
```

Although only one character changed, the ciphertext is almost entirely different. 

A good cipher aims for approximately **50% of the output bits** to change when one input bit changes. 

## **Kerckhoffs's Principle** 

In 1883, **Auguste Kerckhoffs** proposed one of the most important principles in cryptography: 

_A cryptosystem should remain secure even if everything about the system is public knowledge except the secret key._ 

This means: 

- The algorithm can be public. 

- The implementation can be public. 

- The attacker may know exactly how the encryption works. 

- **Only the key must remain secret.** 

Modern encryption algorithms such as AES, RSA, and ChaCha20 all follow this principle. 

## **Security Through Obscurity** 

Keeping an encryption algorithm secret instead of relying on strong mathematics is called **Security Through Obscurity** . 

This approach is **not considered secure** . 

History has shown that once a secret algorithm becomes public, it is often broken quickly. 

## **Real-World Example** 

When you visit an HTTPS website: 

1. TLS uses **asymmetric cryptography** to securely exchange a session key. 

2. After the key exchange, **symmetric encryption (usually AES)** encrypts all subsequent communication. 
 

This combines the strengths of both cryptographic systems. 

## **Key Takeaways** 

- Symmetric cryptography uses one shared secret key. 

- It is much faster than asymmetric encryption. 

- Entropy measures randomness. 

- Hamming Distance counts differing bits. 

- Hamming Weight counts the number of 1s. 

- Claude Shannon introduced the foundations of modern cryptography. 

- Confusion hides relationships between keys and ciphertext. 

- Diffusion spreads plaintext changes throughout the ciphertext. 

- A good cipher exhibits a strong Avalanche Effect. 

- Kerckhoffs's Principle states that security should depend only on the secrecy of the key, not the algorithm. 

---
