# Authenticate

    POST /authenticate
    
Authenticate a customer.



## Parameters
### URI Parameters
None
### Body Parameters
Field | Required | Description
--- | --- | ---
fmd | Y | Fingerprint Minutiae Data, encrypted with the [shared key](/device/ecdh.md)
pin | N | *If not passed, customer_id is required*, encrypted with the [shared key](/device/ecdh.md)
customer_id | N | Your customer identifier
phone | N | 

## Example
### Request

    POST https://api.yombu.com/v1/authenticate
#### Request Body
```json 
{
    "fmd": "xxxxx",
    "pin": "xxxxx",
}
```
### Return
``` json
{
    "success": true,
    "errors": [],
    "access_token": "xxxxx",
    "result": {
      "customer_id": "xxxxx",
    }
}
```
