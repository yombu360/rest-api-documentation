# Delete Customer

    DELETE /customer:bulk
    
Bulk delete customers. This API will remove and sanitize all PII (personally identifiable information) from Yombu's system.



## Parameters
### URI Parameters
None
### Body Parameters
Field | Required | Description
--- | --- | ---
ids | Y | Comma-delimited list of your customer identifiers

## Example
### Request

    DELETE https://api.yombu.com/v1/customer:bulk
#### Request Body
```json 
{
    "ids": "1,2,3"
}
```
### Return
``` json
{
    "removed": true,
    "failed": [],
    "errors": []
}
```
