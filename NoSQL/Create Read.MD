# Create and Read MongoDB Documents #

To create a new document in a collection, you can use the `insertOne()` method. For example, to insert a new document into a "users" collection, you can do the following:
```javascript
app.post('/users', (req, res) => {
  const newUser = req.body;
  db.collection('users').insertOne(newUser, (err, result) => {
    if (err) throw err;
    res.send('User added successfully');
  });
});
```
To read documents from a collection, you can use the `find()` method. For example, to retrieve all documents from a "users" collection, you can do the following:
```javascript
app.get('/users', (req, res) => {
  db.collection('users').find({}).toArray((err, result) => {
    if (err) throw err;
    res.send(result);
  });
});
```