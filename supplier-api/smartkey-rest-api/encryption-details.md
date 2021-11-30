---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# Encryption details

Test over here: [https://www.devglan.com/online-tools/aes-encryption-decryption](https://www.devglan.com/online-tools/aes-encryption-decryption)

* mode: CBC
* keySize: 256
* IV: set in ENV variable ENCRYPTION\_IV
* SecretKey: ENCRYPTION\_SALT => SHA256 => first 32 letters
* outputFormat: Base64
