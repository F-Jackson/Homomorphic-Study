# Symmetric Encryption

## How It Works

Symmetric encryption uses the same key for both encryption and decryption. The process is as follows:

1. **Key Generation**:
   - A single secret key is generated. The same key will be used for both encryption and decryption.

2. **Encryption**:
   - The plaintext data is encrypted using the secret key, transforming it into ciphertext.

3. **Decryption**:
   - The ciphertext is decrypted using the same secret key, returning the original plaintext data.

This method is fast and efficient but requires secure key management to prevent unauthorized access.

---

## AES Algorithm

AES (Advanced Encryption Standard) is one of the most commonly used symmetric encryption algorithms.

- **Key Size**: AES supports key sizes of 128, 192, and 256 bits.
- **Block Size**: AES works on fixed-size blocks of data (128 bits).
- **Rounds**: The number of rounds depends on the key size (e.g., 10 rounds for 128-bit keys).
- **Security**: The encryption strength increases with the key size.

### Example Workflow

1. **Generate Key**:
   - A secret key is generated. 
   - Example: `Secret Key: 0x2b7e151628aed2a6abf7158809cf4f3c`

2. **Encrypt Data**:
   - A plaintext message "HELLO" is encrypted using the **secret key**.
     - Input Message: `HELLO`
     - Encryption Process: The message is transformed using the AES encryption process (involving substitution, permutation, and rounds).
     - Output: `Encrypted Message: 0x39f34a4adcd8086eafbaefca9e9a1d57`

3. **Transmit**:
   - The encrypted message `0x39f34a4adcd8086eafbaefca9e9a1d57` is transmitted.

4. **Decrypt**:
   - The recipient uses the **same secret key** to decrypt the message.
     - Decryption Process: The AES decryption process reverses the transformations to return the original plaintext.
     - Output: `Decrypted Message: HELLO`

---

## Other Symmetric Algorithms

### DES (Data Encryption Standard)

DES is an older symmetric encryption algorithm that uses a 56-bit key to encrypt 64-bit blocks of data.

- **Key Size**: 56 bits
- **Block Size**: 64 bits
- **Rounds**: 16 rounds
- **Security**: DES is now considered insecure due to advances in computing power.

### 3DES (Triple DES)

3DES is an enhancement of DES that applies the DES algorithm three times using either two or three different keys, improving security.

- **Key Size**: 112 or 168 bits (depending on the number of keys)
- **Block Size**: 64 bits
- **Rounds**: 48 rounds (16 rounds per DES operation)
- **Security**: More secure than DES, but still not as secure as newer algorithms like AES.

---

## Summary

- **Symmetric encryption**: Uses a single key for both encryption and decryption.
- **AES**: A widely used and secure symmetric algorithm with variable key sizes.
- **DES/3DES**: Older algorithms, with DES being considered insecure today.
- Symmetric encryption is fast and efficient but requires secure management of the secret key.
