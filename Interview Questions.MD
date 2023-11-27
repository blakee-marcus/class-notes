# Interview Questions

Questions I've been asked during technicals and how I answered, feel free to add your own/change the answers by creating a PR.

### Q: What is a react component?

**A:** A React component is a reusable and self-contained piece of code, it's like a building block for constructing a web page.

### Q: How does JWT work?

**A:** JSON Web Tokens are a compact, URL-safe means of representing claims between two parties. JWTs consist of three parts: a header, a payload, and a signature.

#### Components:

* Header: Specifies the type of token (JWT) and the signing algorithm used. This part is Base64Url encoded.
* Payload: Contains claims, which are statements about the user or entity, and additional data. This part is also Base64Url encoded.
* Signature: Created by taking the encoded header, encoded payload, and a secret or private key, depending on the algorithm, and signing the data.

#### Structure:

* The three components (header, payload, and signature) are concatenated with dots, forming a JWT in the format `xxxxx.yyyyy.zzzzz.`


#### Verification:

* To verify the integrity of a JWT, the receiving party can use the secret or public key to check the signature.
* If the signature is valid, the information in the JWT can be trusted.