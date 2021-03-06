[![CI](https://github.com/eXist-db/expath-crypto-module/workflows/CI/badge.svg)](https://github.com/eXist-db/expath-crypto-module/actions?query=workflow%3ACI)

# eXist-db implementation for EXPath Cryptographic Module

This is an eXist-db implementation of the [EXPath HTTP Crypto Module specification](http://expath.org/spec/crypto).
## Building from source

Requires:
* Java 1.8 or newer
* Maven 3.6 or newer

```bash
$ git clone https://github.com/eXist-db/expath-crypto-module.git
$ cd expath-crypto-module
$ mvn clean package
```

This will create a "expath-crypto-module-<version>.xar" file in the target folder. The .xar file can be uploaded to any eXist-db version > 5.3.0 via the Dashboard.
  
### Currently implemented functions

*   crypto:hash()
*   crypto:hmac() (only for xs:string data for now)
*   crypto:encrypt() (only for xs:string data and symmetric encryption for now)
*   crypto:decrypt() (only for xs:string data and symmetric decryption for now)
*   crypto:generate-signature() (only for XML data for now)
*   crypto:validate-signature() (only for XML data for now)

### Currently implemented algorithms

*   For crypto:hash(): "MD5", "SHA-1", "SHA-256", "SHA-384", "SHA-512".
*   For crypto:hmac(): "HMAC-MD5", "HMAC-SHA-1", "HMAC-SHA-256", "HMAC-SHA-384", "HMAC-SHA-512".

### Documentation

For the latest version of the specification for this module see [http://expath.org/spec/crypto/editor](http://expath.org/spec/crypto/editor).

The implementation follows this specification.

### Unit Tests

Unit Tests use [XQSuite](https://exist-db.org/exist/apps/doc/xqsuite) and can be found in the [src/test/xquery/crypto folder](src/test/xquery/crypto/). 

To run tests:

```bash
$ mvn verify
```