---
cover: ../../.gitbook/assets/skey logo.jpg
coverY: 44.36123348017621
---

# First steps after installation

Every Supplier has its own Blockchain wallet. The seed to this wallet should be included in the .env file.

A valid Supplier wallet needs to have the following properties:

* Valid account script;
* Data entries:
  * `name: string` - name of the organisation
  * `description?: string` - optional - short description of the organisation
  * `type: string = “supplier”`

The setup process can be performed manually or  by sending a POST request to the API endpoint named /utils/setup.

This endpoint will set up the account depending on sent parameters. Sending setScript will upload the script to the blockchain wallet.

IMPORTANT: Make sure the wallet has enough SkeyUSD to perform the transactions.

Available parameters and examples are available here:

[https://dev.orange.api.smartkeyplatform.io/api\_docs/#/utils/UtilsController\_setup](https://dev.orange.api.smartkeyplatform.io/api\_docs/#/utils/UtilsController\_setup)
