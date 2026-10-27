# 🏛️ Topic: Architecture & Core Concepts

Enterprise PKCS#11 (EP11) is engineered specifically for secure coprocessors, cryptographic adapters, and cloud HSM environments. It adheres to PKCS#11 conventions while custom designing state and key management for high-security enterprise environments.

---

## 🔑 Key Architectural Principles

### 1. Stateless Coprocessor Offload
Unlike software tokens or legacy PKCS#11 implementations that maintain stateful sessions in HSM memory, EP11 is designed as a stateless cryptographic coprocessor API. 
* All keys reside on the host system as **Encrypted Key Blobs**.
* When an operation (such as `C_Encrypt` or `C_Sign`) is invoked, the key blob is passed to the HSM, decrypted inside the secure boundary using the Hardware Master Key (WK/MK), executed, and zeroized from temporary registers.

### 2. Encrypted Key Blobs
Key blobs are cryptographically authenticated data structures binding:
* Plaintext key material encrypted under the master key.
* Cryptographic usage flags (`CKA_ENCRYPT`, `CKA_DECRYPT`, `CKA_SIGN`, etc.).
* An HMAC / integrity signature over the payload and attributes.


### 3. Granular Control Points (CPs)
EP11 includes permission bits called **Control Points**. This is how key usage and security policies are enforced. Administrators can enforce cryptographic compliance across an entire crypto domain (e.g., disallowing weak algorithms, enforcing FIPS mode, or restricting key unwrapping).

---

