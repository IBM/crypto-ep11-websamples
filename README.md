# Enterprise PKCS#11 (EP11) Code Samples

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![GitHub Discussions](https://img.shields.io/badge/Discussions-Join_the_Community-brightgreen.svg)](https://github.com/IBM/crypto-ep11-websamples/discussions)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](Contributing.md)
[![Security Policy](https://img.shields.io/badge/Security-Policy-red.svg)](SECURITY.md)

Welcome to the **IBM Enterprise PKCS#11 (EP11) Code Samples** repository. This project provides reference implementations, tutorials, and practical code samples demonstrating how to connect to and build cryptographic applications using the EP11 API in our hardware security modules (HSMs).

---

## 📌 Overview

**EP11 (Enterprise PKCS#11)** is a specialized cryptographic API designed for secure coprocessors, IBM Crypto Express (CEX series). 

Unlike standard PKCS#11 implementations that maintain stateful sessions on the host, EP11 is architected for high-security enterprise environments:
* **Stateless Coprocessor Offload:** Cryptographic state is securely managed using authenticated, encrypted **Key Blobs** protected by a Hardware Master Key.
* **Strict Control Points:** Granular administrative control over allowed mechanisms and key usage attributes through what is called Control Points.
* **Post-Quantum Cryptography (PQC):** Native support for quantum-safe algorithms including ML-KEM (Kyber) and ML-DSA (Dilithium).

---

## 📂 Repository Structure

```
 finish putting this in later once we have the structure completed
```

---

## 🚀 Quick Start & Prerequisites

### 1. Prerequisites
To compile and run these samples, ensure you have:
* A working C/C++ compiler (`gcc`, `clang`, or platform native).
* The **EP11 Client / Host Library** installed on your system (e.g., `libep11.so`, `libep11.dll`, or zCrypt driver).
* Standard PKCS#11 headers (`pkcs11.h`, `pkcs11t.h`, `pkcs11f.h`) and EP11 extension headers (`ep11.h`).
* Access to an EP11 crypto provider (IBM Confidential Computing platform, IBM Z Crypto Express card, or local test emulator).

### 2. General Build & Run Pattern
Each sample directory contains its own `Makefile` or build script and dedicated `README.md`. 

Or 

We have one overall package of samples that gets built from one Makefile.

```bash
# Example: Navigating to a C sample
cd samples/aes

# Build the sample
make

# Run against your EP11 configuration
export EP11_CONFIG=/path/to/ep11client.conf
./aes
```

---

## 📚 Code Sample Catalog

| Sample | Shows |
|--------|-------|
| `00-info` | Connect to an adapter/domain, print module and domain information, check that a wrapping key is present |
| `aes` | Generate an AES-256 key; encrypt/decrypt with AES-CBC-PAD (and AES-GCM where the target offers it) |
| `rsa` | Generate an RSA-2048 key pair; PKCS #1 v1.5 and PSS signatures; OAEP encryption |
| `ec` | Generate P-256 key pairs; ECDSA-SHA256 signatures; ECDH key agreement between two parties |
| `ed25519` | Generate an Ed25519 key pair; EdDSA signatures |
| `hmac` | Generate a generic secret key; HMAC-SHA256 |
| `wrap` | Export (wrap) and import (unwrap) an AES key and an RSA private key under an AES key-encryption key |
| `mldsa` | Post-quantum signatures with ML-DSA (FIPS 204) for ML-DSA-44, -65 and -87: key pair generation, single-shot and Init + Sign sign/verify |
| `mlkem` | Post-quantum key establishment with ML-KEM (FIPS 203), parameter sets 512 / 768 / 1024 |

Each sample prints its steps and ends with `<name>: PASS` (exit code 0) or
`<name>: FAIL` (exit code 1). A step that the target does not support is
reported as `[skip]` and does not make the sample fail.


---

## 💬 Community & Communication

We actively maintain this repository as a hub to connect with developers building on EP11:

* **[GitHub Discussions](https://github.com/IBM/crypto-ep11-websamples/discussions)**: Discuss mechanisms, propose architectures, share ideas, and ask questions.
* **[EP11 Blog & Wiki Articles](wiki/)**: Deep-dive technical articles explaining EP11 architecture, security considerations, and tutorials.
* **[Issue Tracker](../../issues)**: Report bugs with samples or submit a [Sample Request](../../issues/new?template=sample_request.yml).

---

## 🤝 Contributing

We welcome contributions from the community! Whether you are fixing a typo, improving sample documentation, or adding a new sample:

1. Read our [Contributing Guide](Contributing.md).
2. Ensure commits are signed off adhering to the [Developer Certificate of Origin (DCO)](https://developercertificate.org/) (`git commit -s`).
3. Submit a Pull Request following our [PR Template](.github/PULL_REQUEST_TEMPLATE.md).

---

## 📄 License & Security

* Code samples are licensed under the [Apache 2.0 License](LICENSE).
* For reporting security vulnerabilities, please refer to our [Security Policy](SECURITY.md).
