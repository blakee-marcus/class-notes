# CRUD Functions in Mongoose #

CRUD (Create, Read, Update, and Delete) are the four basic operations that can be performed on a database, Mongoose is an Object Data Modeling (ODM) library for MongoDB and Node.js, it provides an easy way to perform CRUD operations on a MongoDB database.

Here is a brief explanation of how CRUD operations can be performed using Mongoose:

1. Create: To create a new document in a collection, you can use the `create()` method of a model. This method takes an object that represents the new document and an optional callback function as arguments.
```javascript
const User = require('./models/User');

const newUser = {
  name: "John Doe",
  email: "johndoe@example.com",
  password: "password",
  age: 30
}

User.create(newUser, (err, user) => {
    if (err) throw err;
    console.log('User created', user);
});
```

1. Read: To read documents from a collection, you can use the `find()` method of a model. This method takes an optional query object and an optional callback function as arguments.
```javascript
const User = require('./models/User');

User.find({ age: { $gt: 30 } }, (err, users) => {
    if (err) throw err;
    console.log('Users found:', users);
});
```

3. Update: To update a document in a collection, you can use the `updateOne()` or `updateMany()` methods of a model. These methods take a query object, an update object, and an optional callback function as arguments.
```javascript
const User = require('./models/User');

User.updateOne({ email: "johndoe@example.com" }, { $set: { age: 35 } }, (err, result) => {
    if (err) throw err;
    console.log('User updated', result);
});
```

4. Delete: To delete a document in a collection, you can use the `deleteOne()` or `deleteMany()` methods of a model. These methods take a query object and an optional callback function as arguments.
```javascript
const User = require('./models/User');

User.deleteOne({ email: "johndoe@example.com" }, (err, result) => {
    if (err) throw err;
    console.log('User deleted', result);
});
```

It's important to note that Mongoose also provides other methods like `findOne()`, `findOneAndUpdate()`, `findOneAndDelete()`, `count()` and others that can be used to perform more complex queries and operations.