# EP11 CKR Return Code Reference & Troubleshooting

*Category: Troubleshooting*

When interacting with the EP11 host library, functions return a `CK_RV` (Cryptoki Return Value). Below are the most common return codes encountered when developing with EP11 and recommended resolution steps.

---

### Common EP11 Return Codes

| Return Code | Hex Value | Common Causes | Resolution |
| :--- | :--- | :--- | :--- |
| **`CKR_OK`** | `0x00000000` | Success | Operation succeeded. |
| **`CKR_PIN_INCORRECT`** | `0x000000A0` | Invalid user or SO PIN supplied to `C_Login`. | Verify PIN configuration in EP11 configuration file or login parameter. |
| **`CKR_MECHANISM_INVALID`** | `0x00000070` | Mechanism not supported by target HSM firmware or disabled by Control Points. | Query `C_GetMechanismList` / `C_GetMechanismInfo` or check HSM Control Point policy. |
| **`CKR_TEMPLATE_INCOMPLETE`** | `0x000000D0` | Missing required attributes in `CK_ATTRIBUTE` array for key generation or derivation. | Ensure all mandatory attributes (`CKA_KEY_TYPE`, `CKA_CLASS`, `CKA_VALUE_LEN`, etc.) are provided. |
| **`CKR_KEY_SIZE_RANGE`** | `0x00000162` | Key length is outside the minimum or maximum supported range for the mechanism. | Verify key bitlength matches mechanism specs (e.g., AES 128/192/256 bits). |
| **`CKR_DEVICE_MEMORY`** | `0x00000031` | Insufficient buffer size or host/device memory allocation issue. | Ensure memory buffers allocated for output data (e.g. ciphertext, signature) match expected length. |
| **`CKR_SESSION_HANDLE_INVALID`**| `0x000000B3` | Session handle closed or never initialized. | Verify `C_OpenSession` succeeded before invoking crypto operations. |

---

### Need Further Assistance?

If you encounter an unexpected `CKR_*` code, start a discussion in our [GitHub Discussions Q&A](https://github.com/IBM/crypto-ep11-websamples/discussions).
