In MongoDB, a cursor is a pointer to the result set of a query. Cursor methods are used to manipulate and retrieve data from the cursor. Some of the most commonly used cursor methods in MongoDB are:
1. `toArray()`: This method returns an array of all documents in the cursor. It can be useful for returning a large number of documents, but be aware that it loads all the documents into memory, which can cause performance issues.

2. `count()`: This method returns the number of documents in the cursor.

3. `sort()`: This method sorts the documents in the cursor by one or more fields. The sort order can be specified as 1 for ascending or -1 for descending.

4. `skip()`: This method skips a specified number of documents in the cursor. It can be useful for pagination.

5. `limit()`: This method limits the number of documents returned in the cursor. It can be used in combination with the skip method for pagination.

6. `forEach()`: This method iterates over all the documents in the cursor and performs a specified action for each one.

7. `map()`: This method applies a specified function to each document in the cursor, returning an array of the results.

8. `next()`: This method returns the next document in the cursor.

9. `hasNext()`: This method returns a boolean indicating whether there are more documents in the cursor.

Cursor methods can be chained together to create complex queries. For example, the following query retrieves the first 10 documents in a collection, sorted by a field called "date", and returns an array of the results:
```javascript
db.collection.find().sort({date:1}).limit(10).toArray()
```

