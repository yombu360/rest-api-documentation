# Create Device

    POST /device
    
Initialize a device for use with Yombu.




## Parameters
### URI Parameters
None
### Body Parameters
Field | Required | Description
--- | --- | ---
rid | N | Reseller ID, supplied by Yombu
mid | Y | Merchant ID, supplied by Yombu
api_key | Y | API key, supplied by Yombu 
mac | Y | MAC address 
public_key | Y | ECDSA public key [How to generate](/device/openssl.md)
location_id | Y | Any alphanumeric string you wish to use to identify a location (there can be multiple devices per location)
address | Y | Street address
address2 | N | Suite, floor, etc
city | Y | 
region | Y | If in the USA, 2 character state code, otherwise local identifier
postal_code | Y | 
country | Y | [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2#Officially_assigned_code_elements) country code

## Example
### Request

    POST https://api.yombu.com/v1/device
#### Request Body
```json 
{
    "rid": "123456789",
    "mid": "123456789",
    "api_key": "xxxxx-xxxxx-xxxxx",
    "mac": "00:00:00:00:00",
    "public_key": "xxxxx",
    "location_id": "12345",
    "address": "1751 Pinnacle Dr",
    "address2": "6th Floor",
    "city": "McLean",
    "state": "VA",
    "postal_code": "22102",
    "country": "US"
}
```
### Return
``` json
{
    "success": true,
    "errors": [],
    "access_token": "xxxxx",
    "result": {
      "location_id": "xxxxx",
    }
}
```
