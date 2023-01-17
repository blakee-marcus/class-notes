# Instance Methods on a Mongoose Model

n Mongoose, an instance method is a function that is added to a model's prototype and can be called on individual documents of that model. Instance methods are useful for adding custom behavior to a document, such as performing calculations or validations.

To add an instance method to a model, you can define a function on the model's prototype. Here is an example of how to add an instance method to a "User" model:

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

userSchema.methods.comparePassword = function (password) {
  return bcrypt.compareSync(password, this.password);
};

const User = mongoose.model('User', userSchema);
```

In this example, I added an instance method called `comparePassword()` to the User model, this method receives one parameter (password) and compare it with the password that is stored in the document (this.password), it returns a boolean indicating whether the password matches or not.

Once you've added an instance method to a model, you can call it on individual documents. For example:
```javascript
User.findOne({email: "johndoe@example.com"}, (err, user) => {
  if (err) throw err;
  if (user.comparePassword("password")) {
    console.log("password match!");
  } else {
    console.log("password don't match!");
  }
});
```
It's important to note that Mongoose also provides other ways to add custom behavior to documents, like statics methods, virtual properties, and middleware that can be used to perform more complex operations.