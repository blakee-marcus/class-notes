# Virtuals in Mongoose

In Mongoose, virtuals are a way to define a property on a schema that does not get persisted to the MongoDB database, but can be used to perform calculations or transformations on the data. Virtuals can be used to provide additional functionality, such as computed properties, or to hide sensitive information from the client.

Here's an example of how to define a virtual property on a User schema:

```javascript
const mongoose = require('mongoose');
const bcrypt = require('bcrypt');

const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
  },
  email: {
    type: String,
    required: true,
    unique: true,
  },
  password: {
    type: String,
    required: true,
  },
  age: {
    type: Number,
    min: 18,
    max: 65,
  },
  createdAt: {
    type: Date,
    default: Date.now,
  },
});

userSchema
  .virtual('passwordConfirmation')
  .get(function () {
    return this._passwordConfirmation;
  })
  .set(function (value) {
    this._passwordConfirmation = value;
  });

const User = mongoose.model('User', userSchema);
```

In this example, a virtual property `passwordConfirmation` is defined on the schema, it doesn't persist to the database, but it can be used to store a confirmation of the password for the user.

Virtuals can also be used to define computed properties that are based on the data in the document, for example, a virtual property that returns the full name of a user, this can be done by defining a getter function for the virtual property:

```javascript
userSchema.virtual('fullName').get(function () {
  return this.firstName + ' ' + this.lastName;
});
```

In this example, the virtual property fullName is defined as a combination of the firstName and lastName fields on the document.

Once virtuals are defined, they can be used like any other property on the document, for example:

```javascript
let user = new User({
  name: 'John Doe',
  email: 'johndoe@example.com',
  password: 'password',
  passwordConfirmation: 'password',
});
console.log(user.passwordConfirmation);
```

Virtuals are a powerful feature of Mongoose, they can be used to perform complex calculations, transform data, and hide sensitive information from the client, but it's important to be aware that virtuals are not stored in the database and are only available on the Mongoose document, not the plain JavaScript object.
