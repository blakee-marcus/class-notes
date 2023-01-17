# Model Schemas in MongoDB using Mongoose #

In MongoDB, a model schema is a blueprint that defines the structure and validation rules for documents in a collection. When using Mongoose, a popular MongoDB object modeling library for Node.js, you can define model schemas using the `Schema` class.

A simple example of a model schema for a "users" collection might look like this:
```javascript
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

const userSchema = new Schema({
  name: { 
    type: String, 
    required: true 
  },
  email: { 
    type: String, 
    required: true, 
    unique: true 
  },
  password: { 
    type: String, 
    required: true 
  },
  age: { 
    type: Number, 
    min: 18, 
    max: 65 
  },
  createdAt: { 
    type: Date, 
    default: Date.now 
  },
});

module.exports = mongoose.model('User', userSchema);
```

In this example, the schema defines a User model with five fields: `name`, `email`, `password`, `age`, and `createdAt`, each field is defined with a property type indicating the type of data that should be expected, and some other properties that are optional, like `required`, `unique` and `default`.

Once a schema is defined, you can use it to interact with the database, for example, to create new users, you can use the `create()` method of the model:
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

Model schemas also provide a way to validate the data before saving it to the database, this is done automatically by Mongoose, if the data passed to the `create()` or `save()` method of a model doesn't match the schema definition, the operation will fail, and an error will be returned.

Model schemas are a powerful tool that can help you structure and validate your data, Mongoose provides several other features like middleware, virtual properties, and pre/post hooks that can be used to add custom logic and behavior to your models.