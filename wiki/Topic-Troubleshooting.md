# ❓ Topic: Troubleshooting & FAQs

Welcome to the EP11 troubleshooting guide and knowledge base. When developing applications against the EP11 API, issues typically arise from configuration mismatches, missing attribute templates, invalid return codes, or permission/control point restrictions.

---

## 🔍 Error Code Diagnostic Reference

If your EP11 API calls return an error (`CKR_*` code):

* 📑 **[EP11 CKR Return Code Reference & Troubleshooting Guide](CKR-Error-Reference)**  
  A detailed breakdown of common return codes such as `CKR_PIN_INCORRECT`, `CKR_MECHANISM_INVALID`, `CKR_TEMPLATE_INCOMPLETE`, `CKR_DEVICE_MEMORY`, and their step-by-step resolutions.

---

## ❓ Frequently Asked Questions (FAQ)

### 1. Why am I getting `CKR_MECHANISM_INVALID` for an algorithm that standard PKCS#11 supports?
EP11 uses **Control Points** configured by your security administrator. If a specific mechanism (like `CKM_DES` or non-standard key wrapping) has been disabled in the domain's Control Point configuration or is deprecated in your firmware level, EP11 will return `CKR_MECHANISM_INVALID`. Check your domain's active control points.

### 2. Why does my key handle fail when passed across different processes?
EP11 keys are managed as encrypted key blobs. If you store only the integer handle `CK_OBJECT_HANDLE` across separate processes without extracting the underlying key blob or using a persistent token, the handle will be invalid in the second process.

### 3. How do I verify my client library configuration?
Ensure your environment variable `EP11_CONFIG` points to a valid configuration file (e.g., `ep11client.conf`), and that the specified socket/port or zCrypt device node (`/dev/z90crypt`) is accessible by the current user.

---
