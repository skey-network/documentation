---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# Generation of key

Procedure for generating a new key in the Skey Network ecosystem is realized through the Supplier API using the POST /keys endpoint. An example of this procedure can be found at this address:

[https://demo.supplier-api.SkeyNetworkplatform.com/api\_docs/#/keys/KeysController\_create](https://demo.supplier-api.skeynetworkplatform.com/api\_docs/#/keys/KeysController\_create)

![Generation of key](https://lh6.googleusercontent.com/1oXe-dKIx4Rr9WW4Y-DOI803pNRsWEX6eKkQFib-gw5Ia8\_G61lO-DLUcv0g22qTgLT3O\_Yc3DUxOxKSg0w2TFJXrdcNATrZnzI8-Dlngq\_sKxEJELq6tuNL4K-7DBsdjnnuXG1s-s-dhb86JFI)

The maximum number of keys that can be created in a single request is 80. If the recipient's address is not provided (by adding the recipient parameter in the payload POST /keys the key is automatically transferred to the specified address after being generated), the created key will remain in the Supplier's wallet. Otherwise, the key will be sent to the recipient address according to the recipient parameter.

The key, which remains in the Supplier wallet after its generation, can be transferred at any time through the endpoint PUT /keys/{assetId}/transfer/{address} in the Supplier API to any address (User).
