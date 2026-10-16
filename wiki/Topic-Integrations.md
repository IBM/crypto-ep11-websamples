# ☁️ Topic: Cloud & Enterprise HSM Integrations

EP11 applications can run across diverse on-premises, mainframe, and cloud environments with consistent API behavior and security guarantees.

---

## 🏢 Target Environments

### 1. IBM Z / Linux on Z (s390x)
* **Overview**: Native integration with IBM Crypto Express (CEX5S, CEX6S, CEX7S, CEX8S) PCIe coprocessors configured in Enterprise PKCS#11 mode.
* **Driver Layer**: Communicates through `zcrypt` kernel module (`/dev/z90crypt`) and `libep11.so`.

### 2. IBM Confidential Computing Platform
* **Overview**: Use Secure Execution containers with Linux technology to safeguard your container workloads and connect to your local hardware based HSM through the EP11 API.
* **Connectivity**: Connect via the EP11 over gRPC / TLS client library or PKCS#11 driver.
* **Master Key Management**: Managed through Smart Card Reader or Key Management CLI.

### 3. Software Emulators & Test Harnesses
* **Overview**: Local mock libraries for CI/CD test automation without physical hardware access.

---

## 📖 Related Articles & Samples
* [Topic: Architecture & Core Concepts](Topic-Architecture)
* [Topic: Troubleshooting & FAQs](Topic-Troubleshooting)
