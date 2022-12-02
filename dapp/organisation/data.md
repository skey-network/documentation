# Data

Data properties:

| Key                                  | Type   | Required | Default value                 | Description                                                                                           |
| ------------------------------------ | ------ | -------- | ----------------------------- | ----------------------------------------------------------------------------------------------------- |
| user\_\<address>                     | string | no       | <p>mobile id<br></p>          | Rgistered user, value is mobile Id, '?' when not set, otherwise device id string or wildcard '\*'     |
| user\_note\_\<address>               | string | no       | **encrypted note**            | Encrypted note about the account set by Organisation used for identification of blockchain addresses. |
| token\_\<assetId>                    | string | no       | **active**                    | Activation token, value: 'active'/'inactive'                                                          |
| manager\_\<address>  => \<publicKey> | string | no       | **binary address of manager** | Binary entry containing blockchain address and public key of a Manager                                |
