# FAQs about Projects

FAQs for projects includes questions about project information.

## How long is the validity of the project certs? 

1 year.

## Who can regenerate the certs? 

Team admin or Publisher can regenerate cert for Publishing projects.
Team admin/Publisher/Subscriber can regenerate cert for Subscribing projects.

## How to encrypt MQTT payloads?

Payload can be encrypted using [JSON Web Encryption](https://en.wikipedia.org/wiki/JSON_Web_Encryption/) or JWE.
Encrypted value of JWE is represented as the concatenation of the Base64 encoded JWE Protected Header, JWE Encrypted Key, JWE Initialization Vector, JWE Ciphertext, and JWE Authentication Tag separated by “.”

BASE64URL(UTF8(JWE Protected Header)) || '.' ||

BASE64URL(JWE Encrypted Key) || '.' ||

BASE64URL(JWE Initialization Vector) || '.' ||

BASE64URL(JWE Ciphertext) || '.' ||

BASE64URL(JWE Authentication Tag)

For **end to end encryption of MQTT payload**, the payload should be **encrypted on the publisher side** and **decrypted on the subscriber side**, Publisher to generate their own encryption keys and manually passing it to subscribers.

**Libraries available for encryption/decryption of JWE**

- [Golang](https://pkg.go.dev/gopkg.in/square/go-jose.v2/)
- [Java](https://connect2id.com/products/nimbus-jose-jwt/)
- [Node](https://github.com/cisco/node-jose/)
- [Python](https://python-jose.readthedocs.io/en/latest/jwe/)
- [Dotnet](https://www.scottbrady91.com/c-sharp/json-web-encryption-jwe-in-dotnet-core/)

**See examples**
- [JWE for payload encryption](https://developer.mastercard.com/platform/documentation/security-and-authentication/securing-sensitive-data-using-payload-encryption/#getting-keys-for-your-application/)
- [Library for client encryption/decryption](https://github.com/Mastercard/client-encryption-go#performing-jwe-decryption/)


