# ECDSA Key Generation

Instructions to generate an ECDSA key pair using OpenSSL for use with Yombu's device registration API

## 
## Commands

**List available ECDSA curves** - We are specifically looking for secp384r1 :  NIST/SECG curve over a 384 bit prime field

`openssl ecparam -list_curves`

**Generate EC private key file**

`openssl ecparam -name secp384r1 -genkey -noout -out private.pem`

**Generate EC public key file**

`openssl ec -in private.pem -pubout -out public.pem`


