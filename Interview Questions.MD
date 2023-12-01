# Interview Questions

Questions I've been asked during technicals. The answers are just examples or talking points, for practice try answering in your own words.

### Q: What is a React component?

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

### How did you use JWT in a project?

**A:** Just explain how you used in a project, i.e, the Auth util file we made in class

### What is MongoDB?

**A:** MongoDB is a NoSQL database management system. Unlike traditional relational databases, which store data in tables with rows and columns, MongoDB follows a document-oriented data model. In MongoDB, data is stored in flexible, JSON-like documents, which are called BSON (Binary JSON) format.

### Explain the `useEffect` hook in React.js

**A:** the `useEffect` hook is used to perform side effects in functional components. Side effects might include data fetching, subscriptions, manually changing the DOM, or other operations that need to happen after the component renders.

### What does the `return` method do in a `useEffect` hook?

**A:** Will be run when the component unmounts or when the dependencies change.

```jsx
useEffect(() => {
  // Code to run after component renders

  // Cleanup function
  return () => {
    // Code to run before the component unmounts or when dependencies change
  };
}, [dependencies]);
```

### How would you align 3 headers in a row inside a div, while only styling the parent div?

