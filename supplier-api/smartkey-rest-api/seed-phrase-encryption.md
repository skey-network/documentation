---
cover: ../../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# Seed phrase encryption

When this API creates a new blockchain account, its seeds are encrypted with AES using crypto-js:

[https://www.npmjs.com/package/crypto-js](https://www.npmjs.com/package/crypto-js)

Example usage:

```
const CryptoJS = require('crypto-js')

function decrypt(message) {
  const salt = 'foobar'
  const iv = '0d8fa75738410842'

  return CryptoJS.AES.decrypt(message, salt, { iv }).toString(CryptoJS.enc.Utf8)
}
```
