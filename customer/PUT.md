# Update Customer

    PUT /customer/{customer_id}
    
Update a customer. Returns the customer object.




## Parameters
### URI Parameters
None
### Body Parameters
Field | Required | Description
--- | --- | ---
first_name | N |
last_name | N | 
customer_id | N | Your customer identifier
phone | N |
fmd1 | N | Optional, additional fingerprint to enroll - must be encrypted with shared key
fmd[2-9] | N | Optional, additional fingerprints to enroll - must be encrypted with shared key
pin | N | Required only for integrations not passing a customer identifier into the [Authenticate API](/authenticate)

## Example
### Request

    POST https://api.yombu.com/v1/customer/2
#### Request Body
```json 
{
    "first_name": "Steve",
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
