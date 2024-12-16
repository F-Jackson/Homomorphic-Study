# Asymmetric Encryption

## How It Works

Asymmetric encryption uses a **public** and a **private** key for secure communication. 

1. **Key Pair Generation**:
   - Keys are generated using algorithms like **RSA**, **ECC**, or **SHA-256**.
   - The **public key** is shared openly, while the **private key** remains secret.

2. **Encryption**:
   - The **public key** encrypts the data.

3. **Decryption**:
   - Only the corresponding **private key** can decrypt the data.

This ensures confidentiality and security of sensitive data.

---

## RSA Algorithm

RSA (Rivest–Shamir–Adleman) is a widely used asymmetric encryption algorithm.

- **Public Key**: For encryption.
- **Private Key**: For decryption.
- **Security**: Relies on the difficulty of factoring large prime numbers.
- **Key Size**: Larger key sizes (e.g., 2048 or 4096 bits) increase security.

### Example Workflow

1. **Generate Key Pair**:
   - A pair of keys is generated using RSA algorithm. 
   - Example: 
     - **Public Key**: `N = 2753, e = 17`
     - **Private Key**: `d = 413`
   
2. **Encrypt Data**:
   - A message "HELLO" is encrypted using the **public key**.
     - Input Message: `HELLO`
     - Encryption Process: Each character is converted to a number and encrypted using the public key formula:
       \[ C = M^e \mod N \]
     - Output: `Encrypted Message: 2791`

3. **Transmit**:
   - The encrypted message `2791` is transmitted.

4. **Decrypt**:
   - The recipient uses the **private key** to decrypt the message.
     - Decryption Process: The encrypted number is decrypted using the private key formula:
       \[ M = C^d \mod N \]
     - Output: `Decrypted Message: HELLO`

---

## ECC (Elliptic Curve Cryptography)

ECC is an efficient asymmetric encryption method using elliptic curves.

- **Key Features**: 
  - Smaller keys (e.g., 256-bit ECC ≈ 3072-bit RSA).
  - High performance and low resource usage.
- **Applications**: IoT, mobile communications, SSL/TLS.
- **Variants**:
  - **ECDSA**: For digital signatures.
  - **ECDH**: For key exchange.
  - **EdDSA**: A faster, modern signature scheme.

### Example Workflow

1. **Generate Key Pair**:
   - A pair of keys is generated using ECC. 
   - Example:
     - **Public Key**: `P = (x1, y1)`
     - **Private Key**: `d`

2. **Encrypt Data**:
   - A message "HELLO" is encrypted using the **public key**.
     - Input Message: `HELLO`
     - Encryption Process: The message is transformed using elliptic curve point multiplication with the public key.
     - Output: `Encrypted Message: (x3, y3)`

3. **Transmit**:
   - The encrypted message `(x3, y3)` is transmitted.

4. **Decrypt**:
   - The recipient uses their **private key** to decrypt the message.
     - Decryption Process: The private key is used to reverse the elliptic curve transformation.
     - Output: `Decrypted Message: HELLO`

---

## Summary

- **RSA**: Generates a pair of keys for encryption and decryption.
- **ECC**: Uses elliptic curves for encryption, generating a smaller but equally secure key pair.
- Both algorithms ensure secure communication by allowing encryption with the public key and decryption with the private key.
