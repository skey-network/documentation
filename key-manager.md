---
cover: .gitbook/assets/skey logo.jpg
coverY: 43.58296622613803
---

# Key Manager

Skey Network Key Manager is a control panel dedicated to service suppliers. It allows access keys for devices to be generated and IoT devices which use our connector to be managed.

The operator of the applications and the systems that provide its services can decide on their parameters. In other words, Key Manager creates smart contracts containing parameters such as: the time of access to sensors or devices, the date of expiry of the contract (access to the device), the cost of access, user verification, and other parameters relevant to a given service.

A service supplier (resource owner), for example a hotel, creates a model contract which it puts up for sale. A given contract is a digital equivalent of a service delivered by the supplier, for example room rental. In creating the contract, the supplier will select basic parameters, such as the period of access to the service, e.g. hotel room, and the method of user verification, e.g. hotel guest. The contract will be visible in the wallet for managing basic keys or paid services. Keys can be created based on the economic parameters of the supplier, so the key can be paid for or free.

Creating a device using Key Manager is done directly through the Supplier API using the POST /devices endpoint and involves generating a blockchain address, uploading the appropriate script to this address and storing the information about it in the Supplier dApp. The new device address must then be stored in the Supplier IoT Platform and paired with a physical device, such as a lock on a hotel room door. This pairing is necessary because further identification will only take place through the blockchain address, and the IoT Platform has to see which physical device is involved.
