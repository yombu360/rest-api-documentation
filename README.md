# Yombu REST API

## Overview
Yombu is a biometric authentication and payments platform. The REST API allows for approved third-parties to connect to the Yombu backend for processing of biometric authentications.

### Support
For API support, please email api.support@yombu.com

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
Each response will include a `status` object and (if successful) a `result` (`result` will be an object for single-record queries and an array for list queries).  The `status` object contains an HTTP `status_code`, `text`, `description`, `error_code` (if an error occurred - see [Error Codes]) and pagination info about the result. The `result` contains the result of a successful request.  For example, a request to the `/services/` resource might return this:

## HTTP Response Codes
Each response will be returned with one of the following HTTP status codes:

* `200` `OK` The request was successful
* `400` `Bad Request` There was a problem with the request (security, malformed, data validation, etc.)
* `401` `Unauthorized` The supplied API credentials are invalid
* `403` `Forbidden` The credentials provided do not have permission to access the requested resource
* `404` `Not found` An attempt was made to access a resource that does not exist in the API
* `405` `Method not allowed` The resource being accessed doesn't support the method specified (GET, POST, etc.).
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
- **<code>POST</code>** [Create Authentication](/authenticate/POST.md)

[Device]: /device/
[Customer]: /customer/
[Authenticate]: /authenticate/
[Error Codes]: /error_codes.md
