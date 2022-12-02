# Data

Data are listed bellow:

* [Device](data.md#device)
* [Device details](data.md#device-details)
* [Physical address](data.md#physical-address)

## Device&#x20;

Data properties:

| Key             | Type                            | Required    | Default value |                                        |
| --------------- | ------------------------------- | ----------- | ------------- | -------------------------------------- |
| name            | string                          | <p><br></p> | <p><br></p>   | Name of the device                     |
| description     | string                          | <p><br></p> | <p><br></p>   | Device description                     |
| type            | string                          | required    | “device”      | Type of entity                         |
| supplier        | string                          | required    | <p><br></p>   | Supplier blockchain address            |
| owner           | string                          | required    | <p><br></p>   | Owner blockchain address               |
| active          | boolean                         | required    | <p><br></p>   | Flag signalling if Device is active    |
| visible         | boolean                         | required    | <p><br></p>   | Flag signalling if Device is visible   |
| connected       | boolean                         | required    | <p><br></p>   | Flag signalling if Device is connected |
| version         | string                          | required    | “1”           | Device dApp version                    |
| lat             | string                          | <p><br></p> | <p><br></p>   | Device latitude                        |
| lng             | string                          | <p><br></p> | <p><br></p>   | Device longitude                       |
| alt             | string                          | <p><br></p> | <p><br></p>   | Device altitude                        |
| custom          | object as stringified JSON      | <p><br></p> | <p><br></p>   | Custom Device properties               |
| key\_\<assetId> | string - “active” or “inactive” | <p><br></p> | <p><br></p>   | Key allowed to perform actions         |
| details         | Object as stringified JSON      | <p><br></p> | <p><br></p>   | Device details - see schema below      |

## Device details&#x20;

Data properties:

| deviceType            | Enum string | <p>Device type</p><p><br></p><p>Supported values:</p><p>'car barrier' | 'human barrier' | 'elevator' |  'human' | 'mobile' | 'other'</p> |
| --------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| deviceModel           | string      | Device model                                                                                                                             |
| additionalDescription | string      | Additional description                                                                                                                   |
| assetUrl              | string      | URL to an optional asset(like an image)                                                                                                  |
| url                   | string      | URL related to the Device                                                                                                                |
| contactInfo           | string      | Contact info to the owner of the Device                                                                                                  |
| physicalAddress       | object      | Physical Address of the Device - see schema below                                                                                        |

## Physical address

Data properties:

| Key          | Type   | Description        |
| ------------ | ------ | ------------------ |
| addressLine1 | string | Device address     |
| addressLine2 | string | Device address cd. |
| city         | string | City               |
| postcode     | string | Postcode           |
| state        | string | State              |
| country      | string | Country            |
| number       | string | Building number    |
| floor        | string | Building floor     |

NOTE: all properties in `Device details` and `Physical address` are **optional**.
