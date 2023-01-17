# Update and Delete MongoDB Documents #

To update a document in a collection, you can use the `updateOne()` or `updateMany()` method. For example, to update a user's name in a "users" collection, you can do the following:
```javascript
app.put('/users/:id', (req, res) => {
  const userId = req.params.id;
  const newName = req.body.name;

  db.collection('users').updateOne({ _id: new ObjectID(userId) }, { $set: { name: newName } }, (err, result) => {
    if (err) throw err;
    res.send('User updated successfully');
  });
});
```

To delete a document in a collection, you can use the `deleteOne()` or `deleteMany()` method. For example, to delete a user from a "users" collection, you can do the following:
```javascript
app.delete('/users/:id', (req, res) => {
  const userId = req.params.id;

  db.collection('users').deleteOne({ _id: new ObjectID(userId) }, (err, result) => {
    if (err) throw err;
    res.send('User deleted successfully');
  });
});
```

