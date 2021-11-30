---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# Seed phrase encryption

When this API creates a new blockchain account, its seeds are encrypted with AES using crypto-js:

[https://www.npmjs.com/package/crypto-js](https://www.npmjs.com/package/crypto-js)

Example usage of decryption using crypto-js:

```
const CryptoJS = require('crypto-js')

function decrypt(message) {
  const salt = 'foobar'
  const iv = '0d8fa75738410842'

  return CryptoJS.AES.decrypt(message, salt, { iv }).toString(CryptoJS.enc.Utf8)
}
```
