# Asymmetric Encryption

## How It Works

Asymmetric encryption uses a **public** and a **private** key for secure communication. 

1. **Key Pair Generation**:
   - Keys are generated using algorithms like **RSA**, **ECC**.
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

## ElGamal Algorithm

ElGamal encryption is based on the Diffie-Hellman key exchange and provides semantic security.

- **Public Key**: Used for encryption.
- **Private Key**: Used for decryption.
- **Security**: Relies on the difficulty of the discrete logarithm problem.

### Example Workflow

1. **Generate Key Pair**:
   - A pair of keys is generated using the ElGamal algorithm.
   - Example:
     - **Public Key**: `(p, g, h)` where `p` is a large prime, `g` is a primitive root modulo `p`, and `h = g^x mod p` for a secret private key `x`.
     - **Private Key**: `x`

2. **Encrypt Data**:
   - A message "HELLO" is encrypted using the **public key**.
     - Input Message: `HELLO`
     - Encryption Process: A random value `k` is chosen, and the message is encrypted as:
       \[
       C_1 = g^k \mod p, \quad C_2 = (h^k \cdot M) \mod p
       \]
     - Output: `Encrypted Message: (C1, C2)`

3. **Transmit**:
   - The encrypted message `(C1, C2)` is transmitted.

4. **Decrypt**:
   - The recipient uses their **private key** to decrypt the message.
     - Decryption Process: The message is decrypted using the formula:
       \[
       M = (C_2 \cdot C_1^{-x}) \mod p
       \]
     - Output: `Decrypted Message: HELLO`
