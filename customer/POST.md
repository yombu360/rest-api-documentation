# Create Customer

    POST customer
    
Create a customer. Returns the newly-created object.




## Parameters
### URI Parameters
None
### Body Parameters
Field | Required | Description
--- | --- | ---
first_name | Y |
last_name | Y | 
customer_id | Y | Your customer identifier
phone | Y |
fmd1 | Y | Initial fingerprint to enroll - must be encrypted with shared key
fmd[2-9] | N | Optional, additional fingerprints to enroll - must be encrypted with shared key
pin | N | Required only for integrations not passing a customer identifier into the [Authenticate API](/authenticate)

## Example
### Request

    POST https://api.yombu.com/v1/customer
#### Request Body
```json 
{
    "first_name": "John",
    "last_name": "Smith",
    "customer_id": "123456789",
    "phone": "555-555-5555",
    "fmd1": "encrypted string",
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
