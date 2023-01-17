# Embedded Documents in MongoDB #

In MongoDB, an embedded document is a document that is stored as a field within another document. This allows for a more flexible and normalized data model, as well as better performance for certain types of queries.

Embedded documents can be used to model one-to-many relationships, where one document is related to multiple other documents. For example, you might have a "users" collection, where each user document has an embedded "orders" field that contains an array of order documents.

The syntax for querying an embedded document is similar to querying a top-level document, but with an additional dot notation to specify the field containing the embedded document. For example, to query for all orders made by a user with a specific email, you might use the following query:

```javascript
db.users.find({"email": "example@email.com"}, {"orders": 1})
```

Embedded documents have some benefits and drawbacks, they can improve the performance of read operations because the data is stored in a single document, it reduces the number of round-trips to the server and also reduces the amount of data that needs to be transferred. On the other hand, embedded documents can make the updates and deletes more complex, specially when you are dealing with large arrays of embedded documents, the size limits of the document can also be a problem.

It's important to note that MongoDB has a limit on the size of a document, which is capped at 16MB, so it's important to consider the size of embedded documents when designing your data model.