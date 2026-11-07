# ⚙️ Topic: Algorithms & Mechanisms

EP11 provides comprehensive hardware-accelerated support for industry-standard symmetric, asymmetric, and post-quantum cryptographic mechanisms.

---

## 🔐 Supported Mechanism Categories

### 1. Symmetric Cryptography
Hardware-accelerated block ciphers and authenticated encryption:
* **AES-GCM (`CKM_AES_GCM`)**: Authenticated Encryption with Associated Data (AEAD).
* **AES-CBC (`CKM_AES_CBC`, `CKM_AES_CBC_PAD`)**: Cipher block chaining mode with PKCS#7 padding.
* **AES-XTS (`CKM_AES_XTS`)**: Storage encryption.
* **AES Key Wrap (`CKM_IBM_AES_KEY_WRAP`)**: Secure key export/import according to RFC 3394 / NIST SP 800-38F.

### 2. Asymmetric Cryptography
Public-key algorithms for key exchange and signatures:
* **ECDSA (`CKM_ECDSA`, `CKM_ECDSA_SHA256`, `CKM_ECDSA_SHA384`, `CKM_ECDSA_SHA512`)**: Elliptic curve digital signature algorithm over standard NIST and Brainpool curves.
* **RSA (`CKM_RSA_PKCS`, `CKM_RSA_PKCS_PSS`, `CKM_RSA_PKCS_OAEP`)**: RSA signatures and encryption up to 4096-bit key sizes.
* **ECDH (`CKM_ECDH1_DERIVE`)**: Elliptic Curve Diffie-Hellman key agreement.

### 3. Message Authentication & Hashing
* **HMAC (`CKM_SHA256_HMAC`, `CKM_SHA512_HMAC`)**: Message authentication codes.
* **SHA-2 / SHA-3**: Secure hashing offloaded to hardware accelerators.

### 4. Post-Quantum Cryptography (PQC)
* **ML-DSA / CRYSTALS-Dilithium (`CKM_IBM_DILITHIUM`)**: Quantum-safe digital signatures.
* **ML-KEM / CRYSTALS-Kyber (`CKM_IBM_KYBER`)**: Quantum-safe key encapsulation.

---