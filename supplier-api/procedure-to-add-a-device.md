---
cover: ../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# Procedure to add a device

The procedure to add a new device to the Skey Network Ecosystem is done through the Supplier API using the POST /devices endpoint. An example of this procedure can be found at this address:

[https://demo.supplier-api.smartkeyplatform.com/api\_docs/#/devices/DevicesController\_create](https://demo.supplier-api.smartkeyplatform.com/api\_docs/#/devices/DevicesController\_create)

![Adding a device](https://lh3.googleusercontent.com/Us3bUGKFOsdynZ-5mJ-UHkgYF9CFSj6rlWOIC63114aJtqVjOUq0nR0cv0zhhau1QbIeL1ccqG7n53fewPiCg49RTYS2nYdBtNBFf57uevAGsidLQT7NZNtJt53u6ouNlzJsbycjAjs7DSkEdJA)

The whole procedure involves generating a blockchain address, uploading the appropriate script to it and storing information about it in the Supplier dApp. The new device address must be stored in the Supplier IoT Platform and paired with the physical device. This pairing is necessary because further identification will only take place through the blockchain address, and the IoT Platform needs to know which physical device is involved.

Additional information such as name and geographical coordinates are also stored in the Data Storage of the device wallet. Fields are defined in advance as the Standard.
