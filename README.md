# Yombu REST API

## Overview
Yombu is a biometric authentication and payments platform. The REST API allows for approved third-parties to connect to the Yombu backend for processing of biometric authentications.

### Support
For API support, please email api.support@yombu.com

### Data Policies
As part of our commitment to data privacy, our most recent biometric privacy policy can be found according to language below in the the [Customer API](/customer) documentation. You must include this in your application and have the customer agree before we can accept any of their data.
* `English` [Unified Biometric Policy](/customer/Unified-Biometric-Policies.docx)
* `Español` [Política Biométrica Unificada](/customer/Unified-Biometric-Policies-ES.docx)

## Authentication
Access to the API is granted by supplying an access token in the header of the request with the key *Access-Token*. To obtain an access token, you will need to register your device with Yombu by using the [Device API](/device). In the response for every successful API request, an access token will be in the body. This access token changes at a random interval.

## API Versioning
The first part of the URI path specifies the API version you wish to access in the format `v{version_number}`.

For example, version 1 of the API os accessible via 

```no-highlight
https://api.yombu.com/v1
```

## HTTP Requests
All API requests are made by sending a secure HTTPS request using one of the following methods, depending on the action being taken:

* `GET` Get a resource or list of resources
* `POST` Create a resource
* `PUT` Update a resource
* `DELETE` Delete a resource

## HTTP Responses
Each response will include a `success` boolean and (if successful) a populated `result` (`result` will be an object for single-record queries and an array for list queries). When a request results in a `422 Unprocessable Entity`, the error object will contain an array of errors and `result` will be empty. When a request results in a `200 OK`, `result` contains the result of the request. A successful API request may look like the following:
```json
{
    "success": true,
    "errors": [],
    "access_token": "xxxxx",
    "result": {}
}
```

## HTTP Response Codes
Each response will be returned with one of the following HTTP status codes:

* `200` `OK` The request was successful
* `400` `Bad Request` There was a problem with the request (security, malformed, data validation, etc.)
* `401` `Unauthorized` The supplied API credentials are invalid
* `403` `Forbidden` The credentials provided do not have permission to access the requested resource
* `404` `Not found` An attempt was made to access a resource that does not exist in the API
* `405` `Method not allowed` The resource being accessed doesn't support the method specified (GET, POST, etc.).
* `422` `Unprocessable Entity` The server understands the content of the request and the syntax of the request is correct, but the server is unable to process the contained instructions.
* `500` `Server Error` An error on the server occurred

#### Note that all dates are in the form of Unix timestamps (seconds since January 1, 1970) and returned in GMT - you will have to account for time zone adjustment depending on your client's location.

## Resources

### [Device][]
- **<code>POST</code>** [Create Device](/device/POST.md)

### [Customer][]
- **<code>POST</code>** [Create Customer](/customer/POST.md)
- **<code>PUT</code>** [Update Customer](/customer/PUT.md)
- **<code>DELETE</code>** [Delete Customer](/customer/DELETE.md)

### [Authenticate][]
- **<code>POST</code>** [Authenticate Customer](/authenticate/POST.md)

[Device]: /device/
[Customer]: /customer/
[Authenticate]: /authenticate/
[Error Codes]: /error_codes.md
