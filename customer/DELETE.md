# Delete Customer

    DELETE /customer/{customer_id}
    
Delete a customer. This API will mark a customer for removal and will trigger an SMS to the end user for confirmation of the removal request. Upon confirmation, all PII will be removed and sanitized.
*If the disconnect flag is passed, no SMS will be sent. The end-user will be disconnected from association with your merchant account.*



## Parameters
### URI Parameters
None
### Body Parameters
Field | Required | Description
--- | --- | ---
customer_id | Y | Your customer identifier
disconnect | N |

## Example
### Request

    DELETE https://api.yombu.com/v1/customer/2
#### Request Body
```json 
{
}
```
### Return
``` json
{
    "success": true,
    "errors": [],
    "access_token": "xxxxx",
    "result": {}
}
```
