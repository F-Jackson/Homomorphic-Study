# Asymmetric Encryption

## How It Works

Asymmetric encryption is a cryptographic system that uses a pair of keys: one **public** and one **private**. Here's the process:

1. **Key Pair Generation**:
   - Two keys are generated using algorithms such as **RSA**, **SHA-256**, **MD5**, or others.
   - The **public key** is shared openly, while the **private key** is kept secret.

2. **Encryption**:
   - The **public key** is used to encrypt the data, ensuring that anyone with access to this key can encrypt messages securely.

3. **Decryption**:
   - Only the corresponding **private key** can decrypt the data, ensuring that only the intended recipient (who owns the private key) can read the message.

This process ensures confidentiality and security for sensitive communications.

---

## RSA Algorithm

RSA (**Rivest–Shamir–Adleman**) is one of the most commonly used algorithms for asymmetric encryption. Key highlights:

- **Public Key**: Used for encryption.
- **Private Key**: Used for decryption.
- **Mathematical Foundation**: Relies on the difficulty of factoring large prime numbers.
- **Security**: The larger the key size (e.g., 2048 bits or 4096 bits), the more secure the encryption.

### Example Workflow Using RSA
1. **Generate Key Pair**:
   - Use libraries like OpenSSL or crypto modules in programming languages (e.g., Python, Node.js).
2. **Encrypt Data**:
   - Encrypt sensitive information using the public key.
3. **Transmit Encrypted Data**:
   - Send the encrypted data to the recipient.
4. **Decrypt Data**:
   - The recipient uses their private key to decrypt the data.