---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# Encryption details

Test over here: [https://www.devglan.com/online-tools/aes-encryption-decryption](https://www.devglan.com/online-tools/aes-encryption-decryption)

* mode: CBC
* keySize: 256
* IV: set in ENV variable ENCRYPTION\_IV
* SecretKey: ENCRYPTION\_SALT => SHA256 => first 32 letters
* outputFormat: Base64
