---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# Generation of key

Procedure for generating a new key in the Skey Network ecosystem is done through the Supplier API using the POST /keys endpoint. An example of this procedure can be found at this address:

[https://demo.supplier-api.SkeyNetworkplatform.com/api\_docs/#/keys/KeysController\_create](https://demo.supplier-api.skeynetworkplatform.com/api\_docs/#/keys/KeysController\_create)

<figure><img src="https://lh5.googleusercontent.com/LNzPST7Dz1iLZrModx06NOPdXchgkFUH5_nkdJD9xFkjWfKHz6B-tBv0_2yFHnNG-KJQmEDGjnvoPu2PBSG3keQBEmWZ8iIgwVTDHo08vfDQHXrMCFpJ8yQuSjG98PqgdAGi0NgiRisRfZKT2e-jVTt39kLPCbTMekX2OQZRF76gk234DYAbJg" alt=""><figcaption><p>Generation of key</p></figcaption></figure>

The maximum number of keys that can be created in a single request is 80. If the recipient's address is not provided (by adding the recipient parameter in the payload POST /keys the key is automatically transferred to the specified address after being generated), the created key will remain in the Supplier's wallet. Otherwise, the key will be sent to the recipient address according to the recipient parameter.

The key, which remains in the Supplier wallet after its generation, can be transferred at any time through the endpoint PUT /keys/{assetId}/transfer/{address} in the Supplier API to any address (User).
