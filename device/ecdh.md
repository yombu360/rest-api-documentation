# ECDH

Instructions on how to generate a shared encryption key between Yombu and approved third parties. 

## 
## Background
Yombu utilizes encryption via ECDH (Ellipic Curve Diffie-Hellman) as an added layer of security for data moving from remote locations to Yombu's backend. ECDH is a key-agreement protocal used by Yombu to faciliate the creation of a shared key without being susceptible to a [Man-in-the-middle attack](https://en.wikipedia.org/wiki/Man-in-the-middle_attack). With ECDH, both parties exchange public keys, then combine the other party's public key with their own private key to create a shared secret.

## Usage
After calling the [Device API](/device), Yombu's current public key will be returned. Combine Yombu's public key with the private key created for the device using a [KDF](https://en.wikipedia.org/wiki/Key_derivation_function), which will create a shared secret. Take the SHA-256 hash of that shared secret to generate a key shared between both the device and Yombu's backend. Store this shared key for usage during symmetric encryption of sensitive data as required by each API.


